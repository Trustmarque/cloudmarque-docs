---
title: IaaS Building Block
summary: Use Infrastructure-as-a-Service technologies to manage traditional datacentre components like VMs, NVAs, and networking.
---
_Infrastructure as a Service_ (IaaS) cloud services provision virtualised infrastructure to run virtual machines. These typically come with a default operating system which is initialised alongside the virtual machine, and thereafter managed by the service consumer.

![A comparison of management responsibilities in On-premise, IaaS, PaaS, and SaaS scenarios](/assets/images/ref-arch/iaas-paas-i.svg)

Operating System configuration, ongoing maintenance, and any middleware, runtime frameworks, data and applications must be managed by the service consumer. The cloud vendor takes reponsibility for the management of physical infrastructure and virtualisation.

## [Hub and spoke networking](/cloudmarque/architecture/iaas/hub-and-spoke.html)
The backbone of any IaaS deployment, the virtual network defines the permitted traffic flow and IP address spaces which resources will be connected to.

Networks may also have [Endpoints](/cloudmarque/architecture/endpoints/) which connect IaaS or PaaS services to on-premises systems or the wider internet.

## [Compute nodes](/cloudmarque/architecture/iaas/compute-nodes.html)
Virtual machines which can host custom application workloads. A compute node may also represent a set of VMs:

 * Enabled for scale (e.g. Azure Scale Sets)
 * With resilience provided by high-availability and/or backup services
 * Configured automatically to support a workload or application

## [Image management ](/cloudmarque/architecture/iaas/images.html)
Create and publish images to be used by _Compute nodes_ and _Virtual desktops_. Applications can be installed dynamically or as part of a base image, enabling shorter startup times with quality-assured images, or with more flexible dynamic application installation at startup.

## [Update management ](/cloudmarque/architecture/iaas/update-management.html)
Set the update cadence and maintenance windows for virtual machines using a tag-based subscription model managed by automation processes.

## [Virtual desktops](/cloudmarque/architecture/iaas/compute-nodes.html)
Remote desktops with managed applications provide stable and secure modern workspaces for employees.