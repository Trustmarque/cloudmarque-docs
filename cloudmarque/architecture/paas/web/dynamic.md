---
title: Dynamic Web Apps
summary: Deploy cloud-enabled apps without worrying about maintenance of the underlying operating systems and middleware.
graphic: stack-paas-web
---
## Definition
A _Dynamic Web App_ provides pre-defined cloud resources with compute frameworks and middleware required for operating web applications and APIs. Dynamic web apps perform compute activity in response to user requests, and so require comprehensive security processes to manage securely. A key advantage of leveraging PaaS-based cloud resources for dynamic web apps is that operating system and middleware updates are carried out by the cloud vendor, reducing the management burden of these resources.

The role of the _Dyanamic Web App_ component is to:

 * Host web applications on a secure compute unit
 * Enable horizontal and vertical scaling to cope with peaks and troughs in user access
 * Offload non-dynamic resources onto alternative web infrastructure
 * Accelerate apps through caching, minimising requests for dynamic content

## Services
Cloudmarque workload components use a [service locator](/cloudmarque/tools/service-locator.html) pattern to identify the services they provide and specify dependencies. This component provides and relies on the following services:

 * ### Capabilities
   This component creates resources with the following service tags:

    * **Apps** - The named application(s) that this component runs.
    * **Web** - A web compute unit for hosting web application user interfaces.
    * **API** - A web compute unit for managing and versioning web APIs.
    * **CDN** - Storage service for accelerating web apps by offloading traffic.

 * ### Dependencies
    * **Logging** - A logging service to track cloud activity.