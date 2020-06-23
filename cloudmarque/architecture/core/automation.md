---
title: Automation
graphic: stack-core-automation
summary: Keep your cloud estate running smoothly by performing maintenance tasks and resolving live issues automatically.
---
## Definition
An _Automation stack_ is a resource (or collection of resources) designed to modify your cloud environment in response to pre-defined triggers. These triggers may be alerts detected in logs, timed maintenance activities, or new resource creation events. The role of the _Automation stack_ is to deliver:

  * Automated service recovery and issue escalation tasks.
  * Resource behaviours that simplify common management tasks.
  * Configuration data for setting up new resources.

An operational _Automation stack_ is an essential part of the Core Building Block. Predefined tag-based behaviours are dependent on the _Automation stack_, which also serves as an extension point for custom behaviours and tasks.

## Services
Cloudmarque workload components use a [service locator](/cloudmarque/tools/service-locator.html) pattern to identify the services they provide and specify dependencies. This component provides and relies on the following services:

 * ### Capabilities
    * **Configurations** - Hosts scripts which configure compute nodes (e.g. [Desired State Configuration](https://docs.microsoft.com/en-us/azure/automation/automation-dsc-overview)).
    * **Management** - Hosts scripts which maintain the cloud environment (e.g. [Runbooks](https://docs.microsoft.com/en-us/azure/automation/automation-runbook-gallery)).

 * ### Dependencies
    * **Keys** - A secret store is required to authorise the automation accounts to access the wider cloud environment.
    * **Logging** - A logging service is required as a target for alerts when automations succeed or fail.