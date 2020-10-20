---
title: Security Building Block
summary: Control access, detect vulnerabilities, and prevent unauthorised activity to secure your organisation and those it serves.
---
Security is a cross-cutting concern relevant to all aspects of Cloudmarque. As a Building Block, it is comprised of several components designed to make secure management of a cloud environment easy to set up and operate.

 * ### [Account Management](/cloudmarque/architecture/security/accounts.html)
   Ensure least-privilege access to cloud environments. This can be achieved by partitioning workloads (separate test and production [environments](/cloudmarque/architecture/devops/environments.html)), using automation to reduce direct user interaction with cloud services, and utilising just-in-time privilege technologies.

 * ### [Partner Access](/cloudmarque/architecture/security/partner.html)
   Give technology partners controlled access your cloud estate to securely enable managed cloud services delivered by third-parties, while retaining ownership of the underlying cloud resources.

 * ### [Security Operations Center](/cloudmarque/architecture/security/soc.html)
   Enable your SecOps Team by plugging in additional tooling to monitor activity in your cloud environment.

 * ### [Governance and Controls](/cloudmarque/architecture/security/governance.html)
   Enforce compliance to organisational standards, wider industry standards, and best practises across your cloud environment. Monitor and mitigate breaches, or prevent them from happening in the first place.

## Defense in depth
The "security onion" below outlines a comprehensive model for defense in depth, in the context of a specific cloud vendor.

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
      <img src="/assets/images/cloudmarque/diagrams/security/layered-security-model-azure.svg" alt="The Security Onion: Defense in depth">
    </div>
  </div>
</div>

While it may appear to be a daunting, complex, and costly exercise to set up a multi-layered defence, many security technologies and products are baked into cloud vendor tooling, included in cloud vendor marketplaces, or provided as part of a product suite providing an easy way to quickly deploy sophisticated tools.

The "security onion" can be understood in four broad categories:

### Proactive Monitoring
Combining [monitoring](/cloudmarque/architecture/core/monitoring.html) with Artificial Intelligence and Machine Learning helps to achieve a balance between comprehensive proactive alerts while also filtering out background noise for the [Security Operations Center](/cloudmarque/architecture/security/soc.html). This capability is typically delivered by SIEM tooling. Azure provides a cloud-native SIEM and SOAR tool called Azure Sentinel, while third party tools can provide equivalent capability using open source tools like [Splunk](https://www.splunk.com/), integrating directly with cloud native APIs and resources.

### Identity and Access (Authentication and Authorisation)
Azure Active Directory P2 includes Azure Identity Protection, Password Protection, Multifactor authentication. AAD P2 can also be purchased as part of EM+S (Enterprise Mobility and Security Suite) which in turn is part of M365. M365 also includes MCAS, the Microsoft CASB solution. So essentially, M365 combined with a SIEM (Sentinel) tool would cover off most of the proactive monitoring stack as well as the Identity and Access stack (Role Based Access Control and Azure Policy are part of the Azure platform and there is no added cost for these).

### Perimeter Security
Establish controls on network traffic using network virtual appliances via IaaS or PaaS services. These can be readily deployed as part of IaaS networking solution such as the [Hub and Spoke pattern](/cloudmarque/architecture/iaas/hub-and-spoke.html). Typical perimeter security includes:

 * Layer 3 and 4 Firewalls (e.g. Azure Firewall, Sophos XG, Barracuda NGF)
 * Layer 7 Application Gateways (e.g. Azure WAF and Front Door, Sophos XG, Barracuda WAF)
 * CASB software with identity and data policy awareness
 * Consider network attached PaaS resources for workloads (storage, BI, internal web apps)
 * Deploy traffic controls on virtual networks and subnets (e.g. Network Security Groups)

### Data protection
Ensure that data is protected at rest and during transit. This can be accomplished by:

 * Enabling encryption at rest by default
 * Using TLS (1.2) when transmitting data between services
 * Leveraging cloud [key stores](/cloudmarque/architecture/core/keys.html) to persist and control access to encryption keys and secrets
 * Manage keys outside of the service in which they are used (e.g. Azure SQL Always Encrypted Column Encryption Keys and Master Encryption keys stored outside of SQL)