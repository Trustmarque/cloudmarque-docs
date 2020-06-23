---
title: Firewall
summary: Secure the perimeter of your cloud environment using "CloudGen" network virtual appliances and services.
graphic: stack-endpoints-firewall
---
## Definition
A _Firewall_ is a basic building block for perimeter security, allowing fine-grained control of the services exposed from one network to another. Both IaaS and PaaS services exist in this area, with a range of vendors and technologies offering management capability across Layer 3, Layer 4, and Layer 7 network traffic.

The role of the _Firewall_ is to:

  * Verify the integrity of traffic flowing between cloud resources and networks
  * Enforce access rules and traffic flow between cloud resources and networks
  * Optionally, transform or re-route traffic to cloud resources (e.g. Layer 7 SSL offload, URL routing)

_Firewalls_ can be used to establish perimeter security for both IaaS and PaaS services. This should be seen as part of a more [comprehensive approach to security](/cloudmarque/architecture/security/).

## Services
Cloudmarque workload components use a [service locator](/cloudmarque/tools/service-locator.html) pattern to identify the services they provide and specify dependencies. This component provides and relies on the following services:

 * ### Capabilities
   This component creates resources with the following service tags:

    * **Gateway** - A new network gateway is published.

 * ### Dependencies
    * **Logging** - A logging service is required to track activity on the network.
    * **Network** - (L3/4 firewalls only) A network location to use for the firewall.
