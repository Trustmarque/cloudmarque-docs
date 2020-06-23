---
title: Account Management
summary: Organise your cloud accounts to easily manage access controls, isolate environments, and simplify cloud navigation and discovery.
graphic: stack-security-accounts
---
## Definition
One of the first decisions to be made when adopting the cloud is how to leverage cloud accounts to help secure your environments. Your cloud estate typically comprises a range of cloud vendors, commercial models, and resource hierarchies. These can be arranged to maximise security by:
 
 1. Simplifying access controls to cloud environments, reducing the likelihood of security incidents arising from overly-complex management systems
 2. Isolating [environments](/cloudmarque/architecture/devops/environments.html), applications, and managed service [partners](/cloudmarque/architecture/security/partner.html) from one another.
 3. Separating live, backup, and test data to reduce the risk of data being used in an incorrect context

## Organisational regimes
Cloud estates can be organised by a range of different attributes:

| Group by     | Examples                    | Comment                                                                      |
|:-------------|:---------------------------:|:-----------------------------------------------------------------------------|
| Application  | `Website`, `ITSM`, `CRM`    | Can be too fine-grained for organisations with many apps. |
| Architecture | `ThreeTier`, `DataCenter`   | Often simplifies relationship between pipelines and cloud resource containers, though this is rarely a cause of inefficiency. |
| Audience | `Customers`, `Partners`, `Internal` | Often simplifies policy management where [governance rules](/cloudmarque/architecture/security/governance.html) differ based on the audience that the resource is serving. |
| Department   | `HR`, `Finance`, `IT`       | Works when support teams are aligned to department. Needs policy for "shared" resources. |
| Environment  | `dev`, `test`, `production` | Often used in conjunction with another grouping mechanism. See also [Environments](/cloudmarque/architecture/devops/environments.html). |
| Partner  | `Stu's Cloud`, `Internal`, `IT LTD` | Useful where a wider cloud estate is managed by a range of service partners. |

In reality it is likely that large cloud estates will incorporate a combination of these regimes, arranged in a hierarchy.

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
      <img src="/assets/images/ref-arch/security-account-hierarchy.svg" alt="Security account hierarchy in Microsoft Azure">
      In this example, a cloud estate is organised using Management Groups, first by whether an estate is managed internally or by a partner. Internally managed resources are then arranged by audience, while partners are arranged by organisation. Test and production subscriptions are then made available within each part of the management group.
    </div>
  </div>
</div>