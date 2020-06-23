---
title: PaaS Building Block
summary: Use Platform-as-a-Service technologies to build and deploy rich cloud-enabled apps with fewer operational responsibilities.
---
The _PaaS_ building block contains solutions for workloads based on higher level cloud services, where details of compute node resources, operating systems, and/or middleware are maintained to a defined SLA as part of the service.

Deploying PaaS workload stacks can reduce the burden on in-house development and operational teams as ongoing maintenance tasks are undertaken by the cloud vendor.

![A comparison of management responsibilities in On-premise, IaaS, PaaS, and SaaS scenarios](/assets/images/ref-arch/iaas-paas-p.svg)

To successfully exploit PaaS services it is important to map the architecture of your application workloads to the appropriate PaaS service. Typically some amount of app transformation is required to refactor the app to optimise use of cloud services, for example:

 - Taking console-based applications and adding components which allow them run as part of a scheduled job
 - Adding application telemetry services to better understand health and availability
 - Changing databases to remove features not available in cloud services

Access to software source code or a strong application vendor relationship are a firm basis for embarking on an app refactoring programme intended to make best use of cloud PaaS services.

## Web
### [Dynamic](/cloudmarque/architecture/paas/web/dynamic.html)
Dynamic web apps provide an engine for driving online human and machine interaction through websites and APIs. Web apps typically rely on middleware technologies which are managed as part of the cloud service, including both server software and frameworks to generate web pages.

A dynamic web stack can run a variety of web-based workloads. Typically the web application `wwwroot` (or equivalent) is uploaded to the service, and configured to select the relevant technology middleware. OS-level interaction is not necessary.

The web stack includes components to secure and monitor web workloads.

### [Static](/cloudmarque/architecture/paas/web/static.html)
Static web sites offer a highly secure, cost-effective approach to delivering websites which do not require server-side application logic. Use cases for static websites include:

 - Web-based documentation, advice, and guidance
 - Marketing microsites and brochureware
 - Browser-based JavaScript apps

A common pattern is to generate static websites from code files as part of a build and deployment pipeline.