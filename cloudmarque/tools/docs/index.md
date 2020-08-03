---
title: Contributing to Docs
summary: As an Open Source project we encourage contributions and feedback; here's how you can get started with documentation.
---
Cloudmarque Docs is a static HTML website built using [Jekyll](https://jekyllrb.com/), the same technology which powers [GitHub Pages](https://pages.github.com/). _docs.trustmarque.com_ is hosted in Microsoft Azure, using the Cloudmarque PaaS component for [static websites](/cloudmarque/architecture/paas/web/static.html).

## About content deployment
Our publishing pipeline can be started by changes in any one of three areas:

 1. ### GitHub: Cloudmarque Docs
    The contents of the Cloudmarque Docs Git repository are packaged raw into an Azure Pipelines artifact and published for consuption by other pipelines (see azure-pipelines.yml in the repository root for more information).

 2. ### GitHub: Cloudmarque PowerShell Tools for Azure
    The Cloudmarque PowerShell Tools for Azure build pipeline generates documentation which is are packaged (as raw Markdown files) into an Azure Pipelines artifact .and published for use by other pipelines.

 3. ### Azure DevOps (TMS Docs Internal)
    Our wider Documentation site content (including our blog, services, and additional help information) triggers the publishing pipeline when new changes are committed to the repository, or when a build is manually triggered.

    The contents of this repository include Trustmarque branding and web assets in the form a [Jekyll site](https://jekyllrb.com/).

The publishing pipeline:

 * Begins by unpacking our Docs Jekyll site
 * Imports the latest published documentation from Cloudmarque Powershell Tools for Azure
 * Imports the latest published documentation for Cloudmarque
 * Runs Jekyll build to turn raw assets into a static HTML website
 * Performs validation tests
 * Publishes the Jekyll site for consumption by further pipelines

Our infrastructure pipeline is triggered by availability of a new published Jekyll site, and:

 * Deploys infrastructure (a Paas Web Static site)
 * Deploys the site content into the infrastructure

## Where to edit
To edit some content, first fork the documentation repository to your own account. Clone the repository:

``` bash
git clone https://github.com/[ACCOUNT]/cloudmarque-docs.git
```

Next, create a new branch to hold your edits. Give this a clear name which describes the types of edit you want to make.

If you intend to make a number of independent edits then consider creating separate branches for each set of related changes. These can then be reviewed and potentially merged in smaller chunks.

``` bash
git checkout -b [BRANCHNAME]
```

Add the main Cloudmarque repository as an upstream source. This will allow you to pull and merge any changes that are made to content while you make your edits.

``` bash
git remote add upstream https://github.com/Trustmarque/cloudmarque-docs.git
```

Pages are written in [Markdown](https://jekyllrb.com/docs/configuration/markdown/), and can be modified with any text editor. Our team use [Visual Studio Code](https://code.visualstudio.com/) (free) as our main editor, often via a browser in [Codespaces](https://online.visualstudio.com/login).

Markdown pages can include HTML markup, in contiguous line blocks.

When you are happy with your changes, commit them with a descriptive message:

``` bash
git commit -S -m "New wordage is of bester"
```

Push your changes to your forked repository:

``` bash
git push -u origin [BRANCHNAME]
```

## Contributing
When you navigate to the branch on GitHub you will now see a new option to **Create pull request**. Fill in a title and then explain the changes that you've made, and why you've made them. For each pull request (PR) please include:

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

Once merged, your contribution will be automatically built and published to the Cloudmarque documentation on [docs.trustmarque.com](https://docs.trustmarque.com/).