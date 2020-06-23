---
title: Governance
summary: Set rules to restrict, enforce, or estabilish behaviours in your cloud environment, helping to achieve security and compliance objectives
graphic: stack-security-governance
---
## Definition
The _Governance_ component of Cloudmarque is concerned with establishing, deploying, and managing rules to constrain the use of cloud resources. These rules can be used to prevent accidental or malicious attempts to manipluate cloud resources to nefarious ends.

The role of _Governance_ is to deliver:

 * The ability to create and deploy rules which regulate cloud environment activity
 * Reporting on rule deployment and compliance
 * Optionally, to provide pre-built rule packs to support specific compliance objectives

Non-cloud resources may be deployed to support these objectives, including Cloud Access Security Brokers (CASB).

## Examples
Rules can be defined to secure resources from a range of security perspectives:

 * **Economic** - Prevent creation of resources at expensive service tiers
 * **Access** - Prevent creation of insecure or publicly available blob storage, or public IP endpoints
 * **Features** - Ensure that cloud resources are properly encrypted
 * **Geography** - Ensure that all resources are in defined regions, to comply with data residency requirements

## Security layers
Cloudmarque advocates a "defense in depth" approach to security. In the _Governance_ space, this relates specifically to the "access control" layer. Using rules enforced natively in the cloud and/or via a CASB, sophisticated resource access controls can be deployed to report or prevent unauthorised activity by users and administrators.

<div class="media mb-4">
  <img class="mr-3" src="/assets/images/ref-arch/security-access.svg" alt="Proactive monitoring" height="128" width="128">
  <div class="media-body">
    <h3 class="mt-0">Access Controls</h3>
    <ul>
      <li>Restrict the types of compute resource which can be deployed, including by type, geography, location, or service level</li>
      <li>Ensure that security features are enabled when an authorised cloud resource is deployed</li>
      <li>Enforce tagging conventions to simplify cloud resource management</li>
    </ul>
  </div>
</div>