---
title: Compute nodes
summary: Virtual Machines are the flexible workhorse compute units of IaaS deployments, requiring careful management processes to maintain healthy systems.
graphic: stack-iaas-compute
---
## Definition
A _Compute node_ is a virtual machine, or collection of virtual machines, designed to run a workload which may incorporate processing and storage elements. This is a traditional virtualised compute capability. The cloud vendor provides the virtual hardware, while the customer is responsible for managing:

 * Operating System settings and updates
 * Framework and middleware deployment, configuration, and updates
 * Software application deployment, configuraiton, and updates

In addition the customer is responsible for:

 * Anti-virus scanning, including malware detection and removal
 * Backups and restoration processes (for non-transient data workloads, or stateful applications)
 * Enabling and configuring encryption processes

The role of the _Compute node_ is to deliver:

  * A collection of virtual resources including:
     * Processing power
     * Memory
     * Persistent storage
  * An initial operating system to manage the virtual resources
  * Connectivity and processes to access and configure the compute node
  * Optionally: resilience and scaling capability

## Services
Cloudmarque workload components use a [service locator](/cloudmarque/tools/service-locator.html) pattern to identify the services they provide and specify dependencies. This component provides and relies on the following services:

 * ### Capabilities
    * **Apps** - Named application services which may be leveraged by other cloud resources or compute nodes.

 * ### Dependencies
    * **Logging** - A logging service is required as a target for alerts regarding the health of the node.
    * **Network** - The network onto which this compute node will be deployed.
    * **Automation (Configuration)** - Configuration scripts for virtual machines to establish a target state.