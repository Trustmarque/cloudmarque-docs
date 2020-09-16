---
title: Deploying via Azure Pipelines
summary: Automate deployments from source code repositories using Cloudmarque PowerShell Tools for Azure and Azure Pipelines.
---
This guide describes how to use Cloudmarque tooling in a more controlled context, with automated rather than manual deployments. We recommend this approach for production environments as it provides consistent repeatable quality with clear troubleshooting and issue remediation processes.

Ideally, environments should be deployed sequentially to an isolated production-like test environment prior to deployment to Prodution. Some workloads are unable to support this approach, and you should [tailor your environment strategy](/cloudmarque/architecture/devops/environments.html) according the constraints of your workload and organisation.

## Principles
Automated deployment brings together several different technologies: source control, pipelines, and infrastructure-as-code. By keeping a code-based definition of the cloud environment in a source code repository (typically Git), a deployment pipeline can be triggered when changes are pushed to a central repository.

![Sequence of local to hosted repositories, to deployment pipeline, to cloud environment](/assets/images/tutorials/pipelines/sequence.svg)

The pipeline takes the contents of the repository and, using a Service Principal, deploys the infrastructure.

This approach ensures that all changes are fully tracked, and enables the use of branching and pull request processes to review and validate changes before deployment. When issues are detected the environment can be reliably rebuilt. Recent and/or relevant changes can reviewed as part of issue triage processes, enabling faster resolution times and higher environment stability.

## Pre-requisites
To follow this guide you must already have several items in place:

 - An instance of **Azure DevOps**. You can [sign up for free](https://docs.microsoft.com/en-us/azure/devops/user-guide/sign-up-invite-teammates?view=azure-devops) to access the required features.
 - A **Git repository** hosted in an Azure DevOps project to [store your code](https://docs.microsoft.com/en-us/azure/devops/user-guide/code-with-git?view=azure-devops)

## Creating a pipeline
A pipeline is a compute resource which carries out the steps defined in a YAML configuration file, typically named `azure-pipelines.yml` and located in the root of your repository. You can create this manually or have one created automatically by Azure DevOps.

![Screenshot of how to set up a new Azure Pipeline](/assets/images/tutorials/pipelines/setup-pipeline.png)

 1. Navigate to your DevOps project
 2. Select the *Pipelines* page, and click on *New pipeline*
 3. Select *Azure Repos Git*, and select your repository
 4. Either choose your existing pipeline or create a new one via the wizard

You can set secret values using the *Variables* [feature](https://docs.microsoft.com/en-us/azure/devops/pipelines/process/variables?view=azure-devops&tabs=yaml%2Cbatch), and then reference the values in the pipeline using the appropriate token.

### Triggering the deployment
Rather than manually requesting a deployment, the pipeline can be automatically configured to execute whenever a change is made to source code in the repository. These rules are set in the YAML pipeline definition.

{% highlight yaml linenos %}
trigger:
  branches:
    include:
      - master
  paths:
    include: # file paths which must match to trigger a build
      - src/*
{% endhighlight %}

In this example, the pipeline will automatically trigger whenever a new commit to the `master` branch is detected which includes changes to any file in the repository's `src` directory (or subdirectories). Using triggers in this way ensures that deployments are initiated automatically as source files change.

### Using the AzurePowerShell task
We recommend using the Azure DevOps Pipeline [AzurePowerShell task](https://docs.microsoft.com/en-us/azure/devops/pipelines/tasks/deploy/azure-powershell?view=azure-devops) to deploy Cloudmarque-aligned architectures. This task provides a PowerShell session with an Azure context, just like you would have if you were running scripts locally.

In the example below, two pipeline variables have been set to make it easier to control the installation scope.

{% highlight yaml linenos %}
variables:
  SCOPE: CurrentUser
  CLOUDMARQUE_AZURE: Cloudmarque.Azure
{% endhighlight %}

The following section shows how to use a single stage deployment running Azure PowerShell from an Ubuntu image. This is then extended with custom PowerShell to deploy the resources you require.

{% highlight yaml linenos %}
stages:
  - stage: Production
    displayName: Deploy to Production environment
    jobs:
      - job: CmAzDeployJob
        pool:
          vmImage: "ubuntu-latest"
        displayName: Deploy Azure Resources
        steps:
          - task: AzurePowerShell@5
            name: CmAzDeploy
            displayName: Deploy Cloudmarque Azure Resources
            inputs:
              azureSubscription: "$(AZURE_SUBSCRIPTION)"
              ScriptType: "InlineScript"
              Inline: |
                # POWERSHELL GOES HERE #
            azurePowerShellVersion: "LatestVersion"
{% endhighlight %}

A specific set of Cloudmarque commands can be used from line **17** to deploy resources. This can be accompanied by any additional commands to tailor settings not included as part of Cloudmarque's PowerShell tools. While Azure connections are set up as part of the AzurePowerShell task, Cloudmarque should also be set up as part of the script. Typically this includes:

 - Installing the module and importing it into the session
 - Setting up the Cloudmarque context with build and pipeline details

A minimal context can be set up for dev environments, but for fully automated environments setting the context will tag your deployed resources with details of the [deploy source information](/cloudmarque/reference/tags/common/cm-source.html), which can greatly assist in triage activities.

{% highlight powershell linenos %}
Install-Module -Name "$(CLOUDMARQUE_AZURE)" -Scope $(SCOPE) -Force
Import-Module -Name "$(CLOUDMARQUE_AZURE)" -Force

Set-CmAzContext `
   -Environment "Production" `
   -ProjectRoot "$(Build.SourcesDirectory)/MyProject" `
   -BuildId "$(Build.BuildNumber)" `
   -BuildRepoName "$(Build.Repository.Name)" `
   -BuildDefinitionName "$(Build.DefinitionName)" `
   -BuildDefinitionNumber "$(Build.DefinitionVersion)" `
   -ProjectConfirmation "y"
{% endhighlight %}

### Deploy resources
With context set, YAML parameter definitions of your environment are used to deploy the resources which correspond to the Cloudmarque Reference Architecture. In the example below we provision a simple static website, capture the outputs, and promote the Storage account and Resource Group names as pipeline variables (so that they can be used in later steps).

{% highlight powershell linenos %}
$outputs = New-CmAzPaaSWebStatic -SettingsFile "$(Build.SourcesDirectory)/MyProject/web.yml"

Write-Host "##vso[task.setvariable variable=STORAGE;isOutput=true]$($outputs.StorageName)"
Write-Host "##vso[task.setvariable variable=RESOURCEGROUP;isOutput=true]$($outputs.ResourceGroupName)"
{% endhighlight %}