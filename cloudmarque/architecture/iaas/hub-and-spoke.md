---
title: Hub and spoke networking
summary: Centralise connectivity for simple and secure management of traffic flow between your cloud environment, on-premises systems, and the internet.
graphic: stack-iaas-networking
---
## Definition
_Hub and spoke networking_ describes a scalable, flexible network topology which fits many cloud environments. It comprises a single _Hub_ network which controls connectivity to on-premises networks and the Internet, alongside a series of _Spoke_ networks which house specific workloads.

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
      <img src="/assets/images/ref-arch/hub-spoke.svg" alt="A hub and spoke network architecture in Microsoft Azure">
    </div>
  </div>
</div>

The role of the _Hub and spoke networking_ component is to deliver:

 * Separation of concerns via network isolation of workloads, which in turn enables:
    * Stable change management (changes can happen in spokes without affecting other services)
    * Independent specialist teams to manage workloads within a specific spoke
 * Centralised provision of management services, forming:
    * A consistent control plane for system connectivity and management
    * Cost-effective deployment and management of infrastructure-oriented appliances and tools

Note that networking can be used to provide connectivity to PaaS services, as well as IaaS based services such as Virtual Machines.

Additional shared services can be deployed into the Hub network, including:

 * Virtual Appliances for security operations, for example Network Taps, Intrusion Detection Systems, and standalone SIEM tools.
 * Load-balanced identity services. For exampl, ADFS may be deployed for improved SSO user experiences (recommended only where direct integration to Azure AD is unavailable)
 * Domain Services, and solutions to manage resources in spokes (licensing optimisation platforms, security suites)

## Services
Cloudmarque workload components use a [service locator](/cloudmarque/tools/service-locator.html) pattern to identify the services they provide and specify dependencies. This component provides and relies on the following services:

 * ### Capabilities
    * **Networks** - Provides a series of subnets which can be used by other cloud resources such as Virtual Machines, Containers, and PaaS resources (storage, web apps, etc).

 * ### Dependencies
    * **Logging** - A logging service is required as a target for network alerts.