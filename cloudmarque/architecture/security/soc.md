---
title: Plugin Security Operations Centre
summary: Connect a SecOps Team to your cloud environment, providing comprehensive data streams for security analysis and incident management.
graphic: stack-security-soc
---
## Definition
The _Plugin SOC_ (Security Operations Centre) component of Cloudmarque is concerned with providing robust and comprehensive event streams of cloud activity for consumption by SecOps teams, typically via additional SIEM tooling which may be deployed inside or outside of a cloud environment.

The role of the _Plugin SOC_ architecture component is to deliver:

 * Event data sources which can be consumed by SecOps security tools
 * Comprehensive activity and event data from cloud resources to relevant data sources
 * "Timely data" which is not too late to act upon (likely a contextual measure, based on the service level objectives of your SOC team)

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
      <img src="/assets/images/ref-arch/security-soc.svg" alt="Plugin Security Operations Center components">
    </div>
  </div>
</div>