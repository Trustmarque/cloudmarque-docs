---
title: Virtual Desktops
summary: Provide secure and flexible desktops to your workforce incorporating the apps and services needed to get their jobs done.
graphic: stack-iaas-wvd
---
## Definition
_Virtual Desktops_ provide a desktop computing experiences from cloud-based infrastructure. These can support multiple sessions (many users using the same compute resource) or be dedicated to a specific user. 

An [Image management](/cloudmarque/architecture/iaas/images.html) component can be used to create the desktop experience for specific user roles, bringing together standard applications and tools. The _Virtual Desktop_ component is responsible for:

  * Delivery of a desktop experience to users.
  * A reliable and secure process for updating apps and desktops.
  * Persisting user settings and data between sessions.

<div class="alert alert-info" role="alert">
  <h4 class="alert-heading">In progress</h4>
  <p>We are currently evaluating new cloud resources which support this architectural component and will be updating this page as we confirm working practises and management processes.</p>
</div>

## Services
Cloudmarque workload components use a [service locator](/cloudmarque/tools/service-locator.html) pattern to identify the services they provide and specify dependencies. This component provides and relies on the following services:

 * ### Capabilities
    * _Virtual Desktop Services do not provide any capabilities which are leveraged by other cloud resources._

 * ### Dependencies
    * **Logging** - A logging service is required as a target for network alerts.
    * **Networks** - Provides connectivity for each desktop host.