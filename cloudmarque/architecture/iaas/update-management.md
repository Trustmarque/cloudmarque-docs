---
title: Update Management
summary: Keep your VM environment up-to-date automatically by leveraging automation and tagging to subscribe to OS update channels.
---
## Definition
Keeping virtual machines up-to-date with the latest operating system (and anti-virus) updates is critical to the stable and secure operation of infrastructure-based workloads. Cloudmarque advocates an automated update process which sees virtual machines "subscribe" to defined deployment cadences based on a predefined tagging convention.

_Update Management_ is responsible for:

  * Automatically installing updates on target VMs
  * Scheduling service windows when systems may be unavailable
  * Setting the types of updates that will be installed

## Services
Cloudmarque workload components use a [service locator](/cloudmarque/tools/service-locator.html) pattern to identify the services they provide and specify dependencies. The Update Management capability is part of the [Automation (Management)](/cloudmarque/architecture/core/automation.html) component.