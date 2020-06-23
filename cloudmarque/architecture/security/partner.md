---
title: Partner Access
summary: Access expertise and manage operational risk by allowing trusted partners to support your cloud estate via robust access control policies.
graphic: stack-security-partners
---
## Definition
Inviting specialists to collaborate with internal staff to build, operate, or review a cloud estate allows organisations to manage risk efficiently. Bringing in experts to support different steps on a cloud journey helps establish robust processes, minimise wasted effort, and optimally apply cloud computing tailored to a specific organisational context.

Making _Partner Access_ a defined component of the security landscape ensures that there are defined mechanisms for partner access control. The role of _Partner Access_ is to deliver:

  * Timely access to cloud resources (on time, and for the necessary duration)
  * The appropriate roles and permissions to manage cloud resources
  * Clear visibility of what access partners have to cloud resources
  * An accurate audit of activities carried out by partners

Non-cloud resources may be deployed to support these objectives, including the use of specialist security tools.

## Security layers
Cloudmarque advocates a "defense in depth" approach to security. For _Partner Access_ this can be evaluated as follows:

<div class="media mb-4">
  <img class="mr-3" src="/assets/images/ref-arch/security-monitoring.svg" alt="Proactive monitoring" height="128" width="128">
  <div class="media-body">
    <h3 class="mt-0">Monitoring</h3>
    <ul>
      <li>Ensure that partner activity (including permission requests) are represented accurately in activity logs</li>
      <li>Establish alerts to identify unexpected partner access to secure resources</li>
    </ul>
  </div>
</div>
<div class="media mb-4">
  <img class="mr-3" src="/assets/images/ref-arch/security-identity.svg" alt="Proactive monitoring" height="128" width="128">
  <div class="media-body">
    <h3 class="mt-0">Identity Protection</h3>
    <ul>
      <li>Agree appropriate identity processes for partners (guest or native identities, security principals, or groups)</li>
      <li>Ensure that identity management tooling encompasses partner accounts</li>
    </ul>
  </div>
</div>
<div class="media mb-4">
  <img class="mr-3" src="/assets/images/ref-arch/security-access.svg" alt="Proactive monitoring" height="128" width="128">
  <div class="media-body">
    <h3 class="mt-0">Access Controls</h3>
    <ul>
      <li>Consider using just-in-time permission approval processes and time-limited access to resources and roles</li>
      <li>Limit access to the resources that the partner is responsible for creating or managing (including backups)</li>
    </ul>
  </div>
</div>
<div class="media mb-4">
  <img class="mr-3" src="/assets/images/ref-arch/security-perimeter.svg" alt="Proactive monitoring" height="128" width="128">
  <div class="media-body">
    <h3 class="mt-0">Perimeter Security</h3>
    <ul>
      <li>Consider using IP restrictions to control partner access to cloud systems</li>
    </ul>
  </div>
</div>
<div class="media mb-4">
  <img class="mr-3" src="/assets/images/ref-arch/security-encryption.svg" alt="Proactive monitoring" height="128" width="128">
  <div class="media-body">
    <h3 class="mt-0">Encryption</h3>
    <ul>
      <li>Unless the partner is working with your data, ensure they do not have access to download data, or the encryption keys used to secure data</li>
      <li>Ensure that backups are also suitably encrypted</li>
    </ul>
  </div>
</div>