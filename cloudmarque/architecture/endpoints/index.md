---
title: Endpoints Building Block
summary: Connect your estate to the Internet, on-premises systems, and third-parties with a range of communication technologies.
---
# Endpoints
Having identified a series of [Infrastructure-as-a-Service](/cloudmarque/architecture/iaas/) and [Platform-as-a-Service](/cloudmarque/architecture/paas/) cloud resources to host IT capability, the planned resources must be connected to the relevant users. These could include:

 * **On-premises** - Connectivity to employees in offices, or remotely working via organisational networks (e.g. VPNs).
 * **Partners** - Connectivity to partner organisations, often for the purpose of B2B automation via APIs.
 * **Public/Users** - Public connectivity, often for the purpose of enabling user self-service of business capability via web sites.

The _Endpoints Building Block_ provides architectural components for securely connecting users to cloud resources.

## [Firewall](/cloudmarque/architecture/endpoints/firewall.html)
Establish perimeter [security](/cloudmarque/architecture/security/) with firewalls. Control traffic flow between your cloud resources and external networks, using both IaaS and PaaS resources.

## [Messaging](/cloudmarque/architecture/endpoints/messaging.html)
Pass data between systems using cloud resources to support a range of messaging patterns.

## [Bastion Hosts](/cloudmarque/architecture/endpoints/bastion.html)
Equip your IT admins with jump-boxes to securely access and manage legacy applications or long-lived infrastructure.