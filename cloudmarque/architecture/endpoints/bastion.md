---
title: Bastion Hosts
summary: Access your cloud environment securely using a "jump box" to perform administrative tasks, including debugging, and triaging issues.
graphic: stack-endpoints-bastion
---
## Definition
A _Bastion_ (jump box) is used by IT staff to manage cloud resources. It is typically configured with scripts, tools, and connectivity to enable IT staff to configure systems and triage issues with cloud resources.

While most modern cloud deployments aim to deploy using [repeatable](/cloudmarque/operations/competencies/ci.html) [DevOps processes](/cloudmarque/architecture/devops/), older legacy applications or resources with long lifecycles (e.g. domain controllers) may require manual configuration activity. Performing these activities may require a direct connection to a virtual machine. Bastion hosts act as a gateway for these administrative tasks to be performed, minimising the potential access points to critical infrastructure.

The role of the _Bastion_ is to:

  * Provide a single, secure access point to manage cloud resources
  * Host tooling required to connect to, and manage, deployed cloud resources

![Diagram showing jump-box architecture](/assets/images/ref-arch/endpoints-bastion.svg)

## Services
Cloudmarque workload components use a [service locator](/cloudmarque/tools/service-locator.html) pattern to identify the services they provide and specify dependencies. This component provides and relies on the following services:

 * ### Capabilities
   This component creates resources with the following service tags:

    * **Bastion** - Each new secret store is given a specific service based on the type of secret it is designed to store.
    * **AdminVm** - A set of management virtual machines, configured with tooling to manage a cloud estate

 * ### Dependencies
    * **Logging** - A logging service tracks activity in the deployed cloud resources.
    * **Keys** - A key service used to secure the provisioned resources.
    * **Automation (Configuration)** - Scripts to automatically install cloud tooling on a target admin machine.