---
title: Messaging
summary: Pass messages between architectural components, to external parties, and to on-premises systems with messaging services.
graphic: stack-endpoints-messaging
---
## Definition
A _Messaging_ component provides the ability to pass data between two systems. This helps to isolate systems from one another by defining mutually agreed data structures that involved parties can publish or consume. The role of _Messaging_ is to deliver:

  * Secure receipt, persistence, and delivery of messages.
  * Support for asynchronous messaging patterns, including advanced concepts such as timeouts
  * Support for guaranteed message delivery, including advanced concepts such as poison message handling
  * Support for distributed delivery patterns, including advanced concepts such as publish/subscribe patterns

In its simplest form, a _Messaging_ component may simply allow storage of messages to be picked up by external systems later. In its most advanced form, and combined with message transformation and orchestration engines, _Messaging_ can be built into a full Enterprise Service Bus and used as the central communication backbone for an organisation's applications.

## Services
Cloudmarque workload components use a [service locator](/cloudmarque/tools/service-locator.html) pattern to identify the services they provide and specify dependencies. This component provides and relies on the following services:

 * ### Capabilities
   This component creates resources with the following service tags:

    * **Queue** - Publishes a queue messaging capability.
    * **PubSub** - Publishes a messaging capability with a publish/subscribe model.
    * **Event** - Publishes a messaging capability as a "fire and forget" event.

 * ### Dependencies
    * **Logging** - A logging service is required to track activity relating to the created messaging services.