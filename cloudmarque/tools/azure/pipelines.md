---
title: Deploying via Azure Pipelines
summary: Automate deployments from source code repositories using Cloudmarque PowerShell Tools for Azure and Azure Pipelines.
---
This guide describes how to use Cloudmarque tooling in a more controlled context, with automated rather than manual deployments. We recommend this approach for production environments as it provides consistent repeatable quality with clear troubleshooting and issue remediation processes.

Ideally, environments should be deployed sequentially to an isolated production-like test environment prior to deployment to Prodution. Some workloads are unable to support this approach, and you should [tailor your environment strategy](/cloudmarque/architecture/devops/environments.html) according the constraints of your workload and organisation.

## Trigger
Rather than manually requesting a deployment, the pipeline can be automatically configured to execute whenever a change is made to source code in the repository.

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

## AzurePowerShell task
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

## Deploy resources
With context set, YAML parameter definitions of your environment are used to deploy the resources which correspond to the Cloudmarque Reference Architecture. In the example below we provision a simple static website, capture the outputs, and promote the Storage account and Resource Group names as pipeline variables (that can be used in later steps).

{% highlight powershell linenos %}
$outputs = New-CmAzPaaSWebStatic -SettingsFile "$(Build.SourcesDirectory)/MyProject/web.yml"

Write-Host "##vso[task.setvariable variable=STORAGE;isOutput=true]$($outputs.StorageName)"
Write-Host "##vso[task.setvariable variable=RESOURCEGROUP;isOutput=true]$($outputs.ResourceGroupName)"
{% endhighlight %}