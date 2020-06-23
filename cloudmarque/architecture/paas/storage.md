---
title: Storage
summary: Provision optimised storage for files, supporting a wide range of data persistence scenarios such as archive, backup, application, and collaboration.
graphic: stack-paas-storage
---
## Definition
_Storage_ enables the provision of resources to persist data. As a PaaS service the storage is elastic and charged on a consumption basis, automatically "right-sized" to the amount of data an organisation needs to store. The role of the _Storage_ component is to deliver:

 * Resilient, persistent storage for data.
 * Cost-optimised storage tiers and management tools based on data access frequency and required availability.
 * Performance-optimised storage based on access patterns.

Key factors to consider when evaluating storage services are:

 * Whether the data needs to be streamed to be useful (read as a byte stream), or should be read as a single block.
 * How resilient your data needs to be across cloud vendor data centers and geographies.
 * Whether data needs to be accessed frequently.
 * Whether data needs to be accessed quickly (the maximum time between requests for the data and the request being fulfilled).

## Services
Cloudmarque workload components use a [service locator](/cloudmarque/tools/service-locator.html) pattern to identify the services they provide and specify dependencies. This component provides and relies on the following services:

 * ### Capabilities
   This component creates resources with the following service tags:

    * **Storage** - Each new storage service can be given a specific service identifier based on the type of storage it provides.

 * ### Dependencies
    * **Logging** - A logging service to track cloud activity.