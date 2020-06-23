---
title: Monitoring
summary: The backbone of an managed cloud environment, Monitoring provides centralised resources for recording and searching events from your cloud environment.
graphic: stack-core-monitoring
---
## Definition
A _Monitoring stack_ is a collection of resources designed to capture and prioritise operational events for insights, troubleshooting, and automation. It is comprise of resources that facilitate both the storage, interrogation, and detection of logged events. The role of the _Logging stack_ is to deliver:

  * A central location for logs to be recorded and interrogated.
  * A data source for detection and triage of estate events.

Centralised logs improve the efficacy of triage and detection processes. This is particularly relevant to security solutions which may draw from a range of audit and log sources to detect security breaches.

## Services
Cloudmarque workload components use a [service locator](/cloudmarque/tools/service-locator.html) pattern to identify the services they provide and specify dependencies. This component provides and relies on the following services:

 * ### Capabilities
   This component creates resources with the following service tags:

    * **Logging** - A service for storing and interrogating event logs from cloud environments.
    * **App Logging** - A service for application-level monitoring services.
    * **Log Store** - A persistent blob or file store for recording cloud events which should not (or cannot) be persisted in the wider searchable log capability. This may be used as a target for "noisy" event sources like verbose network logs.
    * **Notifications**
       * **P1** - Notification channels for priority _one_ alerts: sent immediately for review.
       * **P2** - Notification channels for priority _two_ alerts: sent immediately for review.
       * **P3** - Notification channels for priority _three_ alerts: sent for review at the end of each day.
       * **P4** - Notification channels for priority _four_ alerts: notifications sent at the end of each week for review.
       * **P5** - Notification channels for priority _five_ alerts: notifications which can be summarised and reviewed at the end of each month.

 * ### Dependencies
    * _No dependencies - this is therefore typically the first component to be deployed to a cloud environment by a [DevOps Pipeline](/cloudmarque/architecture/devops/pipelines.html)._