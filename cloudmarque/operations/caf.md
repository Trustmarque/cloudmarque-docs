---
title: Azure CAF Alignment
summary: Microsoft's Cloud Adoption Framework provides holistic best practise guidance for your continued journey to the cloud, to which Cloudmarque is aligned.
---
Microsoft's [Cloud Adoption Framework for Azure](https://docs.microsoft.com/en-us/azure/cloud-adoption-framework/) brings together guidance from Microsoft employees, partners, and customers in an 8-stage lifecycle designed to simplify and accelerate adoption of cloud.

## How Cloudmarque relates to the CAF
Cloudmarque provides common workload patterns designed to work together both technically and in use by operational teams. It is intended to make best practises quickly and consistently attainable through opinionated examples of CAF-aligned deployment and management.

Cloudmarque can therefore be utilised at several points within the CAF lifecycle to provide the concrete patterns and processes which support a productive cloud journey. To use a geographical analogy, if the Cloud Adoption Framework provides a wider map for navigating cloud adoption landscape then Cloudmarque is the tour operator providing pre-packaged guidance and transport to key popular destinations.

![CAF helps you nagivate the landscape, where Cloudmarque provides pre-canned tour routes](/assets/images/cloudmarque/diagrams/operations/caf.svg)

|--------------------|-----------------------------------------|----------------------------------------------------------------|
| Area               | CAF                                     | Cloudmarque                                                    |
|--------------------|-----------------------------------------|----------------------------------------------------------------|
| **Framework type** | Adoption lifecycle                      | Reference Architecture, Operating Model, Optional Tooling      |
| **Cloud support**  | Microsoft Azure, multi-cloud principles | Multi-cloud principles, current implementation Azure-only      |
| **Tooling**        | Azure Quickstarts and Blueprints        | End-to-end delivery tooling aligned to reference architecture  |
| **Design**         | Explains principles and options         | Provides tooling with common default patterns and scenarios    |
| **Services**       | Explains best practises and options     | Reference operating model with managed service implementation  |
|--------------------|-----------------------------------------|----------------------------------------------------------------|

## Touchpoints

  1. ### Where to start: CAF Strategy
     If you're just embarking on your cloud journey in Azure, begin by defining your [Strategy](https://docs.microsoft.com/en-us/azure/cloud-adoption-framework/strategy/) with the Cloud Adoption Framework. It is important that your business drivers, outcomes, and wider business case are well understood.

     Review [partner services](/services) to understand how you might segregate responsibility for cloud resources by workload and across in-house and partner services. This exercise will help you to more accurately model finances on your cloud journey.

  2. ### CAF Planning with Cloudmarque
     The [Plan](https://docs.microsoft.com/en-us/azure/cloud-adoption-framework/plan/) stage is where Cloudmarque begins to shape your journey with clear guidance on decision making, team structures, and responsibilities.

      - Review [Operational Adoption Theory](/cloudmarque/operations/adoption/theory.html) to better understand how optimising flow of work is important to successful delivery.
      - Consider your [Team Design](/cloudmarque/operations/adoption/teams.html) and which of the various DevOps patterns that might suit your team and product(s).
      - Recognise the cultural changes and [competencies](/cloudmarque/operations/competencies/) required to move to cloud, and include these when planning your teams and organisational structures.

     Review the CAF guidance around [organisational alignment](https://docs.microsoft.com/en-us/azure/cloud-adoption-framework/organize/) as part of planning exercises. Pay particular attention to understanding and identifying [anti-patterns](https://docs.microsoft.com/en-us/azure/cloud-adoption-framework/organize/fiefdoms-silos).

  3. ### CAF Ready using Cloudmarque
     A quick and easy way to get started with a [Landing Zone](https://docs.microsoft.com/en-us/azure/cloud-adoption-framework/ready/landing-zone/) is to deploy the Cloudmarque [Core](/cloudmarque/architecture/core/). Deploy Core operational functionality using Infrastructure-as-Code, with deployment pipelines to take your first steps into cloud-based [DevOps](/cloudmarque/architecture/devops/).

     Review the [Adoption Checklist](/cloudmarque/operations/adoption/checklist.html) to understand what other [information systems](/cloudmarque/operations/adoption/systems.html) you will need to put in place.

  4. ### Ongoing management
     Ongoing [governance](https://docs.microsoft.com/en-us/azure/cloud-adoption-framework/govern/) and [management](https://docs.microsoft.com/en-us/azure/cloud-adoption-framework/manage/) scenarios can be implemented as part of ongoing Engineering Team [ceremony](/cloudmarque/operations/ceremony/).

     Aim to reach this stage as soon as possible by including any ongoing maturity improvement objectives in a prioritised Agile Team Backlog. This reduces the "up-front" planning burden by making such improvement activities the responsibility of a business-as-usual team and process.