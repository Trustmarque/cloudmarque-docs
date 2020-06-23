---
title: Source control
summary: Store source code in repositories, specialist storage software designed to help manage the source code that defines your tooling and environments.
graphic: stack-devops-repos
---
## Definition
_Source control_ refers to where the code defining cloud resource creation and orchestration is stored (also referred to as a _Repository_). Source code is loaded from a repository by [deployment pipelines](/cloudmarque/architecture/devops/pipelines.html)and executed, resulting in new cloud resources being created in a target [environment](/cloudmarque/architecture/devops/environments.html).

The role of DevOps _Source Control_ is to deliver:

  * An auditable and complete history of changes to source code
  * Supporting tools and processes for making changes to source code, typically including:
     * The ability to "branch" source code
     * The ability to support controlled change through "pull requests"

## Git
[Git](https://git-scm.com/) is currently the de facto industry standard technology used for source control. It is a _distributed_ version control system. The commands provided by Git are typically used as part of a workflow described as [Git Flow](https://nvie.com/posts/a-successful-git-branching-model/), though GitHub's [simpler variation](https://guides.github.com/introduction/flow/) is also popular.

Git technology is integrated into mainstream source control platforms, including:

 * [Azure DevOps](https://azure.microsoft.com/en-gb/services/devops/)
 * [GitHub](https://www.github.com)
 * [Atlassian BitBucket](https://bitbucket.org/product)

Note that each platform typically provides its own [pipeline tooling](/cloudmarque/architecture/devops/pipelines.html). Though it is often possible to integrate _Source Control_ and _Pipeline_ components from [different platforms](https://docs.microsoft.com/en-us/azure/devops/pipelines/repos/github?view=azure-devops&tabs=yaml), licensing considerations can sometimes make this proposition unattractive.

It is possible to use alternatives to Git as part of Cloudmarque, for example:

 * Microsoft's [Team Foundation Version Control (TFVC)](https://docs.microsoft.com/en-us/azure/devops/repos/tfvc/?view=azure-devops)
 * Apache's [Subversion](https://subversion.apache.org/)

## In Cloudmarque
A typical Cloudmarque deployment comprises three repositories:

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
      <img src="/assets/images/ref-arch/repos.svg" alt="Cloudmarque Source Control Repositories">
    </div>
  </div>
</div>

 1. ### Cloud Resources
    Definitions and scripts to deploy cloud resources across a series of environments.

 2. ### Automation (Configuration)
    Definitions and scripts which configure cloud compute resources (typically VMs/compute nodes).

 3. ### Automation (Management)
    Scripts to manage the cloud environment and automatically respond to alerts.