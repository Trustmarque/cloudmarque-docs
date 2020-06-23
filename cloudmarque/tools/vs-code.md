---
title: Use VS Code with Cloudmarque Azure
summary: Understand the software used to build Cloudmarque PowerShell Tools for Azure and follow instructions for setting up a development environment.
---
This guide walks you through setup of Visual Studio Code as development tooling used to develop Cloudmarque PowerShell Tools for Azure.

Use this guide if you are planning to fork Cloudmarque PowerShell Tools for Azure, including Automation Account Runbooks or deploy pipelines. This gives you the recommended tooling for development, and allows you to extend the framework for your own needs.

## Set up a development environment

   1. ### Install dependencies
      The following pre-requisites are required:

      1. Install [Git](https://git-scm.com/downloads)
      2. Install [PowerShell](https://docs.microsoft.com/en-us/powershell/scripting/install/installing-powershell?view=powershell-7)
      3. Install [Azure PowerShell Modules](https://docs.microsoft.com/en-us/powershell/azure/install-az-ps)

      #### Install Visual Studio Code
      Visual Studio Code (VSCode) is the recommended IDE for developing Cloudmarque.Azure. VSCode is a free IDE developed by Microsoft and the open source community. It is available online via a browser as part of [Visual Studio Online](https://visualstudio.microsoft.com/services/visual-studio-online/), and can also be installed locally across Windows, Mac, and Linux.

      These instructions provide typical defaults for a local installation.

      1. Download and install Visual Studio Code from [https://code.visualstudio.com/]

      2. In the Extensions tab, search for and install:
         * [Material Icon Theme](https://marketplace.visualstudio.com/items?itemName=PKief.material-icon-theme)
         * [PowerShell](https://marketplace.visualstudio.com/items?itemName=ms-vscode.PowerShell)
         * [Prettify JSON](https://marketplace.visualstudio.com/items?itemName=mohsen1.prettify-json)
         * [Azure Repos](https://marketplace.visualstudio.com/items?itemName=ms-vsts.team)
         * [Azure Account](https://marketplace.visualstudio.com/items?itemName=ms-vscode.azure-account)
         * [Liquid](https://marketplace.visualstudio.com/items?itemName=sissel.shopify-liquid)
         * [Sass](https://marketplace.visualstudio.com/items?itemName=Syler.sass-indented)
         * [GitLens](https://marketplace.visualstudio.com/items?itemName=eamodio.gitlens)

      3. Perform any personal quality-of-life changes to customise the environment to your liking:
         * Set your favourite [theme](https://code.visualstudio.com/docs/getstarted/themes)
         * Tweak [settings](https://code.visualstudio.com/docs/getstarted/settings)
         
           **NB:** _Users familiar with Visual Studio Pro/Enterprise may particularly want to set `"workbench.sideBar.location": "right"` to move the side panel (File Explorer, Source Control, Extensions, etc) to the right._

   2. ### Clone the target repository

   ``` bash
   git clone https://www.github.com/Trustmarque/<repo> [local dir]
   ```

   We recommend forking the repository to your own source control system, treating the main public Cloudmarque repository as an upstream source:

   ``` bash
   git remote rename origin upstream
   git remote add origin [your repo]
   ```

   If you want to access an existing topic branch, use:

   ``` bash
   git checkout [branch-name]
   ```

   3. ### Create a development branch

   ``` bash
   git branch topic-<Your feature name>
   ```
