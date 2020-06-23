---
title: DevOps Building Block
summary: Automate provisioning, deploy, and test activities to increase agility and resilience through continuous delivery practises.
---
The _DevOps Building Block_ contains the architecural components which manage the lifecycle and health of cloud resources. This is typically the first layer of technology which needs to be provisioned as part of [adoption processes](/cloudmarque/operations/adoption/), as it enables provisioning of all other components (typically the next component would be [Monitoring](/cloudmarque/architecture/core/monitoring.html) in the [Core Building Block](/cloudmarque/architecture/core/)).

The objective of the _DevOps Building Block_ is to enable:

  * Consistently repeatable deployments
  * Predictable change timeliness with a low failure rate
  * Auditable change history to enable swift triage and remediation

Cloudmarque defines two ways for a cloud environment can be modified. Either:

  1. ### Create new deployments
     You can deploy new definitions of cloud resources via a deployment pipeline. This building block contains this capability.

  2. ### Automated behaviours
     These are defined as part of Core Automation, and can perform remedial actions to establish or maintain the health of an environment. Under normal operations these behaviours should not be invoked manually.

     Think of this capability as the caretaker of your cloud estate. It responds to basic stimulus from the monitoring engine. You don't tell it what to do, it simply carries out actions in response to alert messages. For more, see [Core Automation](/cloudmarque/architecture/core/automation.html).

     Automated behaviours are also managed as part of this building block, as they are defined in code stored in [source control](/cloudmarque/architecture/devops/source.html).

The DevOps Building Block is necessary a necessary part of the Cloudmarque [Operating Model](/cloudmarque/operations/). It underpins three [competencies](/cloudmarque/operations/competencies/) required for operating a cloud environment, including [Code](/cloudmarque/operations/competencies/code.html), [Continuous Integration](/cloudmarque/operations/competencies/ci.html), and [Continuous Delivery/Deployment](/cloudmarque/operations/competencies/cd.html).

## [Source Control](/cloudmarque/architecture/devops/source.html)
Concerned with source code management, maintaining a managed history of code changes over time. This is typically delivered in the form of specialist storage services such as Git repositories.

## [Pipelines](/cloudmarque/architecture/devops/pipelines.html)
Automated pipelines are responsible for taking code from Source Control and performing activities to:

 * Verify integrity of code
 * Validate functionality provided by the code
 * Optimise and package code for deployment
 * Deploy to target environments

## [Environments](/cloudmarque/architecture/devops/environments.html)
Environments are containers of cloud resources which represent independently functional collections of cloud workloads. They are typically isolated (so far as is possible) from external change and managed as a holistic unit.

This overview explains the role of cloud environments and presents options for managing them, alongside benefits and drawbacks. Isolated environments form an important part of quality control processes for cloud environments.