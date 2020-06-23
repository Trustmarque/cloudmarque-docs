---
title: Jobs
summary: Run data processing jobs which leverage the elasticity of the cloud for on-demand, scalable compute power.
graphic: stack-paas-jobs
---
## Definition
A _Jobs_ component provides task-oriented logic and data processing. Task-oriented workloads are particularly cost-effective way to leverage the cloud, as traditional on-premises infrastructure must be permanently provisioned to deal with what may be an irregular flow of tasks.

In the cloud, task-oriented workloads can be have processing power and memory dynamically allocated on-demand. This "horizontal" scaling also allows massive task parallelisation, meaning the overall processing time for a batch of independent tasks is often lower in the cloud as it is not constrained by available hardware. For some services, no charge is incurred while no jobs are being processed, making it a particularly cost-effective way to purchase compute power.

The role of the _Jobs_ component is to deliver:

  * On-demand processing power for independent jobs, from a range of triggers (including [message](/cloudmarque/architecture/endpoints/messaging.html) arrival or scheduled timers)
  * Auto-scaling to support parallelisation of jobs, including control of parallelisation
  * Job health and run history

A common pattern involving _Jobs_ is to provide responsive app user interfaces which invoke long-running or compute-intensive jobs by placing a message on a queue, which invokes the job. This asynchronous pattern prevents apps from being overloaded by processing workloads (an "Denial of Service" when too many users accidentally or maliciously start intensive compute jobs), and avoids user frustration by quickly returning feedback to the user.

## Services
Cloudmarque workload components use a [service locator](/cloudmarque/tools/service-locator.html) pattern to identify the services they provide and specify dependencies. This component provides and relies on the following services:

 * ### Capabilities
   This component creates resources with the following service tags:
    * **Jobs** - Each new secret store is given a specific service based on the type of secret it is designed to store.

 * ### Dependencies
    * **Logging** - A logging service is required by each secret store, and is used as the target store for log events.
    * **Messaging** - (Optionally) Message-based triggers to invoke tasks.