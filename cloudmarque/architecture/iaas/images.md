---
title: Image management
summary: Keep VMs secure and stable by defining how VM disk images are deployed and configured across your cloud estate.
graphic: stack-iaas-images
---
## Definition
_Image management_ is concerned with the lifecycle of creation, management, and retirement for Virtual Machine images. There form the initial virtual disk of a virtual machine deployed as a [Compute node](compute-nodes.html) in an [IaaS Building Block](/cloudmarque/architecture/iaas/). An _Image management_ stack is responsible for:

  * Creation of images with appropriate pre-requisites.
  * Making base images available to virtual machines.
  * Retirement of (and migration from) outdated base images.

There are three different approaches to image management. These are not mutually exclusive. [Tagging standards](/cloudmarque/reference/tags/common/cm-source.html) support tracing the origins of a given disk to assist in retirement processes.

## Approaches
### Base images
Cloud vendors provide a public gallery of base images which are typically optimised for use in their cloud environment and which include components to facilitate communication with the cloud fabric of each vendor, tracing things like CPU and memory usage.

  * **Advantages**
     * Quick and easy to deploy.
     * No need to manage an image library (images managed by cloud vendor).

  * **Disadvantages**
     * No customisation: all configuration must be done _after_ provisioning the VM.

### Dynamic images
Dynamic images are built from a base image at deployment time. After a VM starts up, an extension invokes a script which installs any additional OS components, middleware, or apps and performs additional configuration steps such as domain joining, security hardening, and optimisation.

  * **Advantages**
     * New VMs are always up-to-date with dependent software.
     * No need to manage an image library.
     * Forces adoption of scripting processes to provision and configure VMs.

  * **Disadvantages**
     * Installation and configuration time means a longer wait before the VM is in a usable state.
     * Increased load on network and media storage if many VMs start together and begin installation processes.
     * Without careful versioning procedures, it can be hard to replicate a specific image build as dynamically installed apps are retrieved from artifact repositories.

### Golden images
A "golden image" is a saved VM image that is reused for other VM instances. This can be created manually by starting up a base image from a cloud vendor, installing and configuring the machine, and _then saving the state_ to produce a reusable image (on a Windows machine, the final step would be to run the [sysprep](https://docs.microsoft.com/en-us/windows-hardware/manufacture/desktop/sysprep--generalize--a-windows-installation) tool).

  * **Advantages**
     * New VMs are usable more quickly after startup.

  * **Disadvantages**
     * There can be significant overhead dealing with management and versioning of images.
     * Where the golden image build is not automated, there can be difficulties delivering new images with consistent timeliness and quality.
