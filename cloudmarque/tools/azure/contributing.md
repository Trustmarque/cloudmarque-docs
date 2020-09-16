---
title: Contributing to Azure Tooling
summary: As an Open Source project we encourage contributions and feedback; here's how you can extend and change the framework.
---
*Cloudmarque PowerShell Tools for Azure* is a collection of PowerShell Cmdlets in the form of a PowerShell module. It can be used to quickly and efficiently provision a working cloud environment aligned to the [Cloudmarque Reference Architecture](/cloudmarque/architecture/).

## Raising an issue
Before starting work on a new feature or bugfix, please review the status of open [issues](https://github.com/Trustmarque/cloudmarque-azure-pwsh/issues) in GitHub.

 - If there is **already an open issue**, review the current status and identify the branch where the issue/feature is being addressed. Fork this branch and communicate with any issue collaborators in the main thread.
 - If there is **no open issue**, create one. Mark it as a *bug* or *enhancement* as appropriate, and give as much detail as possible regarding the problem or proposed feature.

You can wait for a member of the community to review and potentially deliver the change, but as an Open Source project you are able to carry the change forward yourself.

## Making changes
To develop new features or make changes, first fork the tooling repository to your own account by clicking on "Fork", and selecting your desired account. This will create a copy of the tooling repository in your GitHub acount.

![GitHub fork option](/assets/images/tutorials/contributing/fork-github.png)

You can then clone this repository to your local development machine using `git clone`, along the lines of:

``` bash
git clone https://github.com/[ACCOUNT]/cloudmarque-docs.git
```

Next, create a new branch to hold your edits. Give this a clear name which describes the types of edit you want to make. If you intend to make a number of independent edits then consider creating separate branches for each set of related changes. These can then be reviewed and potentially merged in smaller chunks.

``` bash
git checkout -b [BRANCHNAME]
```

Add the main Cloudmarque repository as an upstream source. This will allow you to pull and merge any changes that are made to content while you make your edits.

``` bash
git remote add upstream https://github.com/Trustmarque/cloudmarque-azure-pwsh.git
```

Our team use [Visual Studio Code](https://code.visualstudio.com/) (free) as our main editor, often via a browser in [Codespaces](https://online.visualstudio.com/login). In the root of the repository are a handful of helper scripts which aid in development. Load these via:

``` powershell
. .\init.ps1 # Loads the helper CmdLets
```
 - `Sync-CloudmarqueAzure` - Reloads the module into the current session to make changes visible.
 - `Test-CloudmarqueAzure` - Runs Pester tests (including code style analysis).
 - `Build-CloudmarqueAzure` - Refreshes the PowerShell module manifest with public functions.

Please validate that all [Pester](https://github.com/pester/Pester) tests pass before submitting your pull request for review. To run these, use `Test-CloudmarqueAzure`. Where possible, add your own tests to verify key functionality of any cmdlets you have changed or added.

When you are happy with your changes, commit them with a descriptive message:

``` bash
git commit -S -m "New wordage is of bester"
```

Push your changes to your forked repository:

``` bash
git push -u origin [BRANCHNAME]
```

## Contributing
Navigate to the Cloudmarque GitHub repository and in the *Pull Requests* tab, select **New pull request**. Click *Compare across forks* if you don't see your own repository. Select the relevant branch, then fill in a title and then explain the changes that you've made, and why you've made them. For each pull request (PR) please include:

 1. Your motivation for making changes.
 2. A paragraph stating how widespread the changes are.
 3. Whether imagery/diagrams need to be updated, and whether these are included in the PR.
 4. Links or references evidencing that any guidance or advice is best practise (or otherwise).
 5. A picture of a cute animal is not mandatory, but encouraged.

We'll then review the changes and use the Pull Request thread to communicate whether we're in a position to merge the contribution.

<div class="alert alert-info" role="alert">
  <h4 class="alert-heading">Contributor Licence Agreement</h4>
  <p>
    Before your contribution is merged to Cloudmarque we ask that you complete a <a href="http://wiki.civiccommons.org/Contributor_Agreements/">Contributor Licence Agreement</a>. This allows you to retain copyright of the contributed material while promising not to exercise typical powers that copyright implies, enabling the community to be confident that their use of Cloudmarque is free from legal encumberances.
  </p>
</div>

Once merged, your contribution will be automatically built. We don't publish every build to the [Cloudmarque.Azure PowerShell Gallery](https://www.powershellgallery.com/packages/Cloudmarque.Azure/), but your change should be included in the next major release.