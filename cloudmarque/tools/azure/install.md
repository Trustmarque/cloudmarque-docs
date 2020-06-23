---
title: Cloudmarque PowerShell tools for Azure
---
## Step 1: Install
Cloudmarque PowerShell tools for Azure is published to the [Powershell Gallery](https://www.powershellgallery.com/packages/Cloudmarque.Azure/) and can be installed like any PowerShell package:

{% highlight powershell %}
Install-Package -Name "Cloudmarque.Azure" -Scope CurrentUser
{% endhighlight %}

Dependencies will be automatically installed.

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
  * `_tags` - Contains YAML descriptions of your automatic tagging convention
  * `core` - An example YAML deployment which provisions a Core building block

By convention, any project-related settings reside in directories beginning with an underscore. Any resources deployed to your environment reside in directories with no underscore prefix.

You may wish to manage your project via source control: you should commit the whole directory to your SCCM system, for example by running `git init` in the newly created directory.
