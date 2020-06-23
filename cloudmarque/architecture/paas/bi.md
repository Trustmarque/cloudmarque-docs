---
title: Business Intelligence
summary: Deploy a modern technology stack for extracting, consolidating, and transforming data which is then disseminated to users.
graphic: stack-paas-bi
---
## Definition
A _BI_ stack brings together cloud resources for data storage, transformation, and publishing to deliver a comprehensive platform for delivering Business Intelligence capabilities to an organisation or department. The role of the _BI stack_ is to:

 * Receive, persist, and safely erase historical data.
 * Transform, combine, and aggregate data to produce meaningful insights.
 * Visualise data.
 * Allow secure, personalised, controlled access to data.
 * Perform advanced analysis including predicting trends.
 * Trigger actions when actual or predicted measures reach defined thresholds.

## Services
Cloudmarque workload components use a [service locator](/cloudmarque/tools/service-locator.html) pattern to identify the services they provide and specify dependencies. This component provides and relies on the following services:

 * ### Capabilities
   This component creates resources with the following service tags:

    * **Storage** - A storage location for inbound data.
    * **DB** - A database for processed data
    * **BI Processing** - A compute resource for carrying out ETL processes (either on demand or via message triggers)
    * **Visualisation** - A compute resource for visualising the data, rendering graphs and dashboards

 * ### Dependencies
    * **Logging** - A logging service to track cloud activity.