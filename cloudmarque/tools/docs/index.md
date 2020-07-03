---
title: Editing Docs
summary: As an Open Source project we encourage contributions and feedback; here's how you can get started with documentation.
published: false
---
Cloudmarque Docs is a static HTML website built using [Jekyll](https://jekyllrb.com/), the same technology which powers [GitHub Pages](https://pages.github.com/). _doc.trustmarque.com_ is hosted in Microsoft Azure, using the Cloudmarque PaaS component for [static websites](/cloudmarque/architecture/paas/web/static.html).

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
