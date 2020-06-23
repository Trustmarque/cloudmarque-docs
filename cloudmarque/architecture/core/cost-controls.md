---
title: Cost controls
graphic: stack-core-costs
summary: Control your cloud spend with alerts and warnings to ensure you don't receive any surprise bills!
---
## Definition
A _Cost control stack_ is a collection of resources designed to manage consumption-based spend. This comprises a set of spend limits and alert rules to control the financial risks associated with cloud-based spend. Including this stack in the Core Building Block ensures that every cloud estate has baked-in financial controls. The role of the _Cost control stack_ is to deliver:

  * Defined budgets with spend limits over some time period.
  * An spend breach notification process aligned with wider alert management.
  * Granular spend controls operating within a wider tagging standard.
  * Recommendations for optimising the cost profile of resources.

Budgets should be set when a project is initialised and regularly updated. Close co-ordination with your organisation's Finance team is recommended.

## Tags
Cost management is controlled by the standard tag `cm-charge` which can be applied to any resource. For more information on use of this tag, please see the [cm-charge tag reference](/cloudmarque/reference/tags/common/cm-charge.html).

## Services
Cloudmarque workload components use a [service locator](/cloudmarque/tools/service-locator.html) pattern to identify the services they provide and specify dependencies. This component provides and relies on the following services:

 * ### Capabilities
   _This component does not publish any services._

 * ### Dependencies
    * **Logging** - A logging service is required as a target for alerts when budgets are breached.
