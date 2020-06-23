---
title: Core Building Block
summary: At the heart of every subscription is a Core Building Block containing the resources that manage the health of your estate.
graphic: block-core
---
_Core_ houses "cross-cutting" concerns that apply to all resources. There are six capability stacks in Core which form the foundation of good cloud service management.

Deploying Core is a straightforward first step toward building the operational capability of your cloud estate.

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
      <img src="/assets/images/ref-arch/block-core.svg" alt="Cloudmarque Core Azure Monitoring Solution">
    </div>
  </div>
</div>

## [Keys](keys.html)
A _Keys_ stack is a specialist store for certificates, passwords, keys, and tokens. This integrates with other cloud services to allow for secure dissemination of access controls.

Whether you are encrypting VM disks, enforcing SSL on websites, or configuring connections to SQL databases in a DevOps pipeline, the secure value should be put into a secret store. Almost every resource will require some kind of access control key, so a secret store is a critical part of your Core architecture.

## [Tagging](tagging.html)
While not a resource in itself, a standardised _Tagging_ stack enables clearer operational processes and automation possibilities. A good tagging strategy allows resources to participate in pre-defined automation behaviours and defines relationships between resources and wider service concepts. For example:

 * Marking resources for [automated deletion](/cloudmarque/reference/tags/common/cm-delete.html)
 * Associating resources with [owner operator](/cloudmarque/reference/tags/common/cm-owner.html) contact information
 * Recording the [source](/cloudmarque/reference/tags/common/cm-source.html) of a resource

## [Monitoring](monitoring.html)
Concerned with the storage and management of logs across the cloud environment. Alongside the ability to search and interrogate logs are options around metrics to be tracked, alert thresholds, and onward incident processing when these thresholds are breached.

Monitoring must be deployed and [integrated into wider cloud operational processes](/cloudmarque/operations/adoption/).

## [Automation](automation.html)
Changes to cloud environments can take one of two paths:

 * Redeployments from defined source code repositories
 * Changes driven by cloud automation (this component)

Standard Operational Procedure can be defined and carried out by Automation accounts. These procecures can further be triggered to run when some threshold or specific alert type is detected in the monitoring stack, potentially making an environment self-healing and reducing the burden on Service Desk teams.

## [Cost controls](cost-controls.html)
Consumption-based charging can be a blocker to cloud adoption. As costs are not predictable, typical financial controls may be ineffective. New tools and processes are needed to monitor spend and quickly react to unexpected consumption. The Budget stack includes tooling to track and control spend tied into operational process.

The _Cost Control_ stack also includes associated cost optimisation configuration options.