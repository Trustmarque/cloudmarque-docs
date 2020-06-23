---
title: Keys
summary: Secure your cloud environment with centralised lifecycle management of keys for access control and encryption.
graphic: stack-core-keys
---
## Definition
A _Key stack_ is a resource (or collection of resources) designed to maintain sensitive system access values. These may take the form of secrets, passwords, tokens, or certificates. The role of the _Key stack_ is to deliver:

  * Secure storage of key values.
  * Secure provision of keys to cloud resources and automated processes.
  * Retirement of keys upon expiry or renewal.

Secrets are typically created by external systems or apps, not by the _Key stack_ itself.

## Services
Cloudmarque workload components use a [service locator](/cloudmarque/tools/service-locator.html) pattern to identify the services they provide and specify dependencies. This component provides and relies on the following services:

 * ### Capabilities
   This component creates resources with the following service tags:

    * **Secrets** - Each new secret store is given a specific service based on the type of secret it is designed to store.

 * ### Dependencies
    * **Logging** - A logging service is required by each secret store, and is used as the target store for log events.
