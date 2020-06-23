---
title: Environments
summary: Configure multiple cloud environments to verify the integrity of deployment code and establish quality controls on the "path to live".
graphic: stack-devops-environments
---
## Definition
DevOps _Environments_ are logically separated operational units of cloud resources. [Code](/cloudmarque/architecture/devops/source.html) to [deploy](/cloudmarque/architecture/devops/pipelines.html) defined cloud resources is executed in a target environment, resulting in new instances of the cloud resources being created.

The role of DevOps _Environments_ is to deliver:

  * Segregated areas for cloud deployments and reconfigurations to be validated.
  * A foundation for quality control processes (appropriate to workloads being deployed).

_Environments_ support a range of quality control processes:

  * ### Sequential
    Code is deployed to environments sequentially. The deployment sequence can be modified with as many steps as required, the most basic example being deployment to a _Test_ environment before deployment to a _Production_ environment.

  * ### Sequential with parallelism
    Code is deployed to some environments in parallel. Cloud resources could be deployed to _Test_ environment and to a _Penetration Testing_ environment in parallel, and relevant quality control tests executed.
    
    This is a less popular configuration as it trades cost for delivery time: you will pay for creating and running both environments, when failure in either one would prevent continuing with a deployment to a Production environment. However, if both tests succeed, then time to the Production environment is reduced.

    It is usually more efficient to execute quality control processes sequentially, in order of risk (tests with the greatest probability of failure preventing a deployment are executed first).

## Tooling support
Cloudmarque Tooling employs two strategies for managing multiple cloud environments:

  1. ### Contextual cues
     PowerShell tooling requires that a user explicitly states which environment they are interacting with via a cmdlet. This information can be used by cmdlets to set appropriate system behaviours.

  2. ### Naming
     Cloudmarque generates resource names automatically according to defined naming conventions, making cloud environments easier to understand and navigate. This naming convention includes the current environment being used. By using the target environment as part of a naming convention, it is considerably harder to accidentally deploy to the wrong environment. In addition, this approach supports resources which require globally unique names.

## Environment segregation strategies
There are several ways to provide environment segregation, and options vary between cloud vendors.

  * ### Azure

     * **Tenant** - Deploy separate Azure AD tenants for each test environment. This will result in separate user accounts required between test and live. These accounts must be licensed separately. While appropriate in some edge cases where the tenant configuration represents a part of the service under test, the additional management and licensing overhead makes it economically difficult to justify.

     * **Subscription** - Deploy separate Azure subscriptions for each test (and production) environment. This is the most common pattern, providing a clear security and financial container for each environment. This boundary corresponds neatly with the typical scope of cloud tools, making side effects from tool execution much less likely.

     * **Resource** - Deploy resources to the same Azure subscription and denote items for deployment with a robust naming convention to delineate resources. This option allows more efficient use of some cloud resources, for example running test and production versions of a web site within the same compute node. However, it is essential that management tooling is used carefully to only modify expected resources from either Automation or DevOps Pipelines.

It is advisible to set up cost management tools and processes to manage test environments.

  * **Nightly wipes** - Destroy test environments at a regular cadence to minimise spend. For example, running a script to empty the environment every day, every few hours, or automatically after quality control processes have been executed.

## Services
Cloudmarque workload components use a [service locator](/cloudmarque/tools/service-locator.html) pattern to identify the services they provide and specify dependencies. This component does not have any dependencies nor provide explicit services in the cloud environment, as it is the environment.