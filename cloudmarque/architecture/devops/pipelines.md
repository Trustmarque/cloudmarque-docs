---
title: CI/CD Pipelines
summary: Continuous Integration and Deployment pipelines provide automation for creating and changing cloud environments.
graphic: stack-devops-pipelines
---
## Definition
A _CI/CD Component_ is a compute resource responsible for taking cloud environment definitions, parameters, and tooling and orchestrating quality control processes to consistently verify and deploy these to target cloud environments. This brings together compute capability to follow defined workflows and storage capability for persisting outputs (including process metadata and/or records of deployed components).

This is a specialist compute workload, with a range of consumption options including self-managed infrastructure-as-a-service, managed platform-as-a-service, or fully-managed software-as-a-service.

The role of a _CI/CD Component_ is to deliver:

  * Automated integration of cloud environment control software (build, aggregation, or compilation)
  * Automated testing and verification of cloud environment definitions and tooling
  * Automated deployment of cloud definitions using relevant tooling

Alongside [Automation](/cloudmarque/architecture/core/automation.html), Pipelines should be the only resources permitted to make changes to a cloud environment.

## Competencies
Both [Continuous Integration](/cloudmarque/operations/competencies/ci.html) and [Continuous Delivery and Deployment](/cloudmarque/operations/competencies/cd.html) are [competencies](/cloudmarque/operations/competencies/) described in the Cloudmarque Operating Model. Pipelines are a [required system](/cloudmarque/operations/adoption/systems.html) to implement the Cloudmarque Operating Model, providing a robust mechanism to control change in a cloud environment.

## Services
Cloudmarque workload components use a [service locator](/cloudmarque/tools/service-locator.html) pattern to identify the services they provide and specify dependencies. This component does not have any dependencies nor provide explicit services in the cloud environment, as it is part of the control plane for the environment.