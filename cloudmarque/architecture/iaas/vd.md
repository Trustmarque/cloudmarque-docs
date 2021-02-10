---
title: Virtual Desktops
summary: Provide secure and flexible desktops to your workforce incorporating the apps and services needed to get their jobs done.
graphic: stack-iaas-wvd
---
## Definition
_Virtual Desktops_ provide a desktop computing experiences from cloud-based infrastructure. These can support multiple sessions (many users using the same compute resource) or be dedicated to a specific user. 

An [Image management](/cloudmarque/architecture/iaas/images.html) component can be used to create the desktop experience for specific user roles, bringing together standard applications and tools. The _Virtual Desktop_ component is responsible for:

  * Delivery of a desktop experience to users.
  * A reliable and secure process for updating apps and desktops.
  * Persisting user settings and data between sessions.

<div class="card text-center">
  <div class="card-header">
    <ul class="nav nav-tabs card-header-tabs" role="tablist">
      <li class="nav-item">
        <a class="nav-link active" data-toggle="tab" href="#azure" role="tab" aria-controls="profile" aria-selected="true">Azure</a>
      </li>
    </ul>
  </div>
  <div class="card-body tab-content">
    <div class="tab-pane show active" id="azure" role="tabpanel" aria-labelledby="azure-tab">
      <img src="/assets/images/cloudmarque/diagrams/architecture/iaas/wvd.svg" alt="Architecture for Windows Virtual Desktop in Microsoft Azure">
      <hr>
      <div class="text-left">
        <h4>Key components</h4>
        <p>The general architecture of an Azure Windows Virtual Desktop solution is outlined in the diagram. The following narrative additions identify a range of decision points.</p>
        <dl>
          <dt class="icon icon-azure-bastion">Bastion hosts <em>(Optional)</em></dt>
          <dd>Not strictly part of the WVD solution, a typical hub infrastructure will include jumpboxes loaded with administrative tooling and accessed via the Azure Bastion service.</dd>
          <dt class="icon icon-azure-wvd">Windows Virtual Desktop Pools</dt>
          <dd>Virtual Desktops can be dedicated to individuals (personal) or utilise shared virtual infrastructure in a pool. Application groups are used to publish apps to workspaces for users to consume. New pools can be brought online with updated applications.</dd>
          <dt class="icon icon-azure-fslogix">FSLogix User Profiles</dt>
          <dd>Host user profiles in Premium Azure Storage account with File Share via a Private Endpoint and using AADDS (or equivalent IaaS solution) for authentication. NetApp Files may also be used and may fit some scenarios with requirements for high availability.</dd>
          <dt class="icon icon-azure-lighthouse">Lighthouse Managed Services <em>(Optional)</em></dt>
          <dd>Safely grant third-parties access to your infrastructure to provide management and maintenance services using Azure Lighthouse.</dd>
          <dt class="icon icon-azure-packer">Image Management</dt>
          <dd>Golden images can be built from templates using technologies like Packer in Pipelines, or as part of the Azure Image Builder service, and deployed to Shared Image Galleries.</dd>
          <dt class="icon icon-azure-aadds">Directory Services</dt>
          <dd>Directory Services are currently a required component of the WVD stack, and can be provisioned through PaaS-based AADDS or a self-hosted IaaS VM (which may suit regional HA scenarios). Additionally, provisioning ADFS can address a known issue with multiple required logins.</dd>
        </dl>
      </div>  
    </div>
  </div>
</div>

## Updates, patches, and release management
The recommended approach to delivering new updates into a Virtual Desktop environment is using blue-green deployment of new desktops as part of a [strangler pattern](https://docs.microsoft.com/en-us/azure/architecture/patterns/strangler-fig). An example process involves:

 1. Creating a new base image containing OS updates, refreshed middleware, or application patches.
 2. Deploying the new image to a new pool with a limited set of users (perhaps a champions group or test team).
 3. _For mature environments, running automated tests to verify app functionality._
 4. Publishing the new Virtual Desktop experience once verification is complete.
 5. Disabling new connections to the current/legacy Virtual Desktop experience.
 6. When all connections are drained, decommissioning the legacy Virtual Desktops or refreshing them with the next set of updates.

## Services
Cloudmarque workload components use a [service locator](/cloudmarque/tools/service-locator.html) pattern to identify the services they provide and specify dependencies. This component provides and relies on the following services:

 * ### Capabilities
    * _Virtual Desktop Services do not provide any capabilities which are leveraged by other cloud resources._

 * ### Dependencies
    * **Logging** - A logging service is required as a target for network alerts.
    * **Networks** - Provides connectivity for each desktop host.