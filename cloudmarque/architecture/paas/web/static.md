---
title: Static Web Sites
summary: Serve information-based microsites and browser-based apps using high performance, low cost cloud services.
graphic: stack-paas-web
---
## Definition
A static web site allows users to access web resources that requires no server-side application processing.

With no compute resource required to generate the web resources, static sites have unique characteristics:

 - they are low-latency as resources can be heavily cached
 - they are highly scalable, with no compute resource forming a CPU/memory bottleneck
 - they have a smaller attack profile, as there is no server-side application code to exploit
 - they are cheap to host and run

<div class="card text-center">
  <div class="card-header">
    <ul class="nav nav-tabs card-header-tabs" role="tablist">
      <li class="nav-item">
        <a class="nav-link active" data-toggle="tab" href="#azure" role="tab" aria-controls="profile" aria-selected="true">Azure</a>
      </li>
    </ul>
  </div>
  <div class="card-body tab-content">
    <div class="tab-pane show active" id="azure" role="tabpanel" aria-labelledby="azure-tab">
      <img src="/assets/images/ref-arch/block-paas-web-static.svg" alt="Architecture for a static website in Microsoft Azure">
    </div>
  </div>
</div>

## Workloads
The static website stack is an ideal candidate for the following workloads:

 - Web-based documentation, advice, and guidance
 - Marketing microsites and brochureware
 - Browser-based JavaScript apps (which might use interactive APIs from other sites)

With low costs, static websites are a good platform for testing out innovative ideas which might otherwise be cost or complexity-prohibitive to deliver via a traditional dynamic web app.

## DevOps Integration
A static website works best when managed from [source control](/cloudmarque/architecture/devops/source.html). A configured build pipeline can be used to both build the static website assets and deploy the cloud infrastructure. Example tools include:

 - [Jekyll](https://jekyllrb.com/) which powers [GitHub Pages](https://pages.github.com/)
 - [Gatsby](https://www.gatsbyjs.org/)

Source control can also be used as a basic content management system such as [Netlify](https://www.netlifycms.org/), allowing an interactive editing experience from the browser. Multi-stage deployment pipelines can also be leveraged to provide staging environments for publishing previews.

## Tools
To deploy a new static website, use the `New-CmAzPaaSWebStatic` command. Documentation is provided in the [command reference](/cloudmarque/reference/commands/new-cmazpaaswebstatic.html).

``` powershell
New-CmAzPaaSWebStatic -SettingsFile "c:\source\azure\mysite\paas.web.static.yml"
```