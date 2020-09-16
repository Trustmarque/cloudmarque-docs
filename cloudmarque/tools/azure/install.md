---
title: Cloudmarque PowerShell tools for Azure
summary: Download Cloudmarque tools on your local machine to support development and experimentation scenarios.
---
This guide describes how to install Cloudmarque on a development server, a typical scenario for DevOps and Cloud Engineers who need to experiment with quickly creating and destroying environments.

<div class="alert alert-info" role="alert">
  <h4 class="alert-heading">Local vs. pipeline installation</h4>
  <p>
    Deployments to test or production environments should be deployed via automated pipelines, typically triggered by changes to a configuration repository. The process is functionally identical to the one outlined below and outlined in a [separate guide](/tools/azure/pipelines.html).
  </p>
</div>

## Prerequisites
Before installing Cloudmarque PowerShell Tools for Azure, you will need:

 * PowerShell (we recommend the latest stable version of [PowerShell 7](https://github.com/PowerShell/PowerShell/releases))

## Step 1: Install
Cloudmarque PowerShell tools for Azure is published to the [Powershell Gallery](https://www.powershellgallery.com/packages/Cloudmarque.Azure/) and can be installed like any PowerShell package. Create a new PowerShell session and enter the following command:

{% highlight powershell %}
Install-Package -Name "Cloudmarque.Azure" -Scope CurrentUser
{% endhighlight %}

![Console window showing PowerShell commands and output after installing the Cloudmarque.Azure package](/assets/images/tutorials/install/01.png)

Alternatively you can omit the `Scope` parameter to install the package for all users, though you will need to be running your PowerShell console as an Administrator. Use `-Force` if you don't want to be prompted to approve the source, or where the installation may be unattended.

Dependencies are specified within the package and will be automatically installed.

## Step 2: Import
To use commands from the package, import the PowerShell module into your current session:

{% highlight powershell %}
Import-Module -Name "Cloudmarque.Azure"
{% endhighlight %}

## Step 3: Create a project
Cloudmarque PowerShell tools for Azure operate in the context of a project. A project is a folder containing definitions of resources to be deployed, pipelines that deploy them, and conventions that apply to them. To create a new template project in a new directory use the following command:

{% highlight powershell %}
New-CmAzProject -Project "MyProject"
{% endhighlight %}

This will create a new project in the current directory with the name "MyProject". In the project you will find the following folders:

  * `_names` - Contains YAML descriptions of your cloud resource naming convention
  * `*.yml` - Example YAML deployments which provision different parts of the Cloudmarque archtiecture

By convention, any project-related settings reside in directories beginning with an underscore. Any resources deployed to your environment reside in directories with no underscore prefix.

Alternatively you can build your project folder manually using settings from another project you have worked on, or from settings provided from tutorials or public repositories.

You may wish to manage your project via source control: you should commit the whole directory to your SCCM system, for example by running `git init` in the newly created directory.

## Step 4: Connecting to Azure
Many Cloudmarque commands require your Azure Context to be set, and will gracefully fail if this is not available. Connect to your Azure subscription as you normally would, with commands similar to:

``` powershell
Connect-AzAccount
Get-AzSubscription -SubscriptionId "<SUBSCRIPTION>"-TenantId "<TENANT>" | Set-AzContext
```

## Step 5: Set your Cloudmarque context
Next you need to provide Cloudmarque with information about the project you are working with, including the naming conventions, tags, and deployment resources to use. We do this by setting the _Cloudmarque Azure Context_ to the project directory you created in step 3.

`Set-CmAzContext -ProjectRoot "C:\Source\CloudmarqueDemo\MyDemo\"`

![Console window showing PowerShell output of the Cloudmarque Context](/assets/images/tutorials/install/02.png)

You can also set a range of other properties on the CmAzContext which define which environment you are operating in, and the source of the changes you are making. See the documentation for the [Set-CmAzContext](/cloudmarque/reference/commands/set-cmazcontext.html) for more information.

The Cloudmarque Context retains information on the source of the deployment, repositories, and tooling versions. These are deployed as tags on resources which can be used to diagnose issues later on.

While it is less important for the context to be set in development scenarios, these properties should be explicitly reviewed and configured when Cloudmarque is used in a pipeline deployment targeting controlled environments (i.e. environments where resource deployments are automated).

## Step 6: Deploy sample workloads
The first part of any cloud deployment should be [Core workloads]/cloudmarque/architecture/core/), including monitoring, automation, and key vaults. Publishing Core services provides a foundation for other services to use later. Try running the following commands:

``` powershell
New-CmAzCoreMonitor -SettingsFile "monitor.yml"
New-CmAzCoreKeyVault -SettingsFile "keyvaults.yml"
New-CmAzCoreBillingRule -SettingsFile "budgets.yml"
```

You are now ready to move on to designing and deploying your desired architecture, which will be the subject of a future tutorial.