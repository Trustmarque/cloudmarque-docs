---
title: Information Systems
summary: Review the information systems described by the Cloudmarque Operating Guide alongside selection guidance and characteristics.
---
The Operating Model is supported by a series of Information Systems. This page describes the role of these systems and pertinent characteristics but does not mandate a particular technology or approach: tooling selection should be based on organisational context.

## Knowledge Base
The Knowledge Base serves as process documentation for the Service Desk team, describing how to respond to known issues, perform incident triage, and route incidents to relevant specialists or service providers.

Key characteristics of the Knowledge Base include:

 - Owned by Service Desk
    - Content should be "accepted" by the Service Desk Team when provided by the Engineering Team
 - Must be accessible by both Service Desk staff and Engineering Team
 - Ability to quickly search the Knowledge Base to find relevant instructions

Potential tools to implement a Knowledge Base include:

 - Microsoft SharePoint (Shared documents in [Teams](https://www.microsoft.com/en-gb/microsoft-365/microsoft-teams/group-chat-software), or a [Wiki](https://support.office.com/en-gb/article/create-and-edit-a-wiki-dc64f9c2-d1a2-44b5-ac59-b9d535551a32))
 - Generated Static Sites (e.g. [Jekyll](https://jekyllrb.com/), [Gatsby](https://www.gatsbyjs.org/))

## Documentation
The Documentation system serves as technical tooling documentation for the Service Desk team, describing how to install, run, and configure available service tooling. This should include implementation-agnostic explanations of tool parameters and usage, describing tool features with example usage.

Key characteristics of the Documentation site include:

 - Owned by Engineering Team
 - Must be accessible by both Service Desk staff and Engineering Team
 - Ability to quickly search the Knowledge Base to find relevant documentation
 - Partially or fully generated automatically from input documentation

Potential tools to implement a Documentation site include:

 - Generated Static Sites (e.g. [Jekyll](https://jekyllrb.com/), [Gatsby](https://www.gatsbyjs.org/))
 - [Sandcastle](https://www.red-gate.com/simple-talk/dotnet/net-tools/taming-sandcastle-a-net-programmers-guide-to-documenting-your-code/) (.NET tooling)

## ITSM
An ITSM system is designed to track the lifecycle of customer or user incidents or service requests which typically take the form of a "ticket" that unifies communication with the relevant parties to address a specific problem or change.

Key characteristics of the ITSM system include:

 - Owned and accessible by the Service Desk team
 - Ability to model the parties involved in raising and resolving tickets
 - Ability to support the service and processes of your organisation:
    - Establish, warn, and track SLAs where applicable
    - Perform handover between multiple teams where necessary
 - Support the necessary communication channels for your organisational context (e.g. email, IM, phone)
 - Manage ticket anonymisation and removal of personal details over time

There are many open source and proprietary ITSM solutions, and most organisations likely already at least one deployed which can be utilised as an implementation of the Operating Guide.

## Pipelines
A deployment pipeline tool takes source code from a source code repository and transforms it into a functioning system in one or more target environments. This is a key technical enabler for two competencies: [Continuous Integration](/cloudmarque/operations/competencies/ci.html) and [Continuous Deployment](/cloudmarque/operations/competencies/ci.html).

Key characteristics of a Deployment Pipeline CI/CD system include:

 - Owned by the Service Desk team
 - Ability to execute tasks in your cloud technology of choice:
    - For Cloudmarque, this is recommended to support PowerShell in an Azure context
 - Support for code quality automation, including formatting, testing, and reporting
 - Support for multi-stage sequential deployments, ideally with approval gateways
 - Should be the only system entitled to make changes in target deployment environments

`Cloudmarque.Azure` tooling is designed and tested to work in [Azure DevOps Pipelines](https://azure.microsoft.com/en-gb/services/devops/pipelines/).

## Backlog
A backlog is maintained in an information system which supports task management. Some teams may only require a very lightweight solution which allows capture of a deliverable component (or, "user story") and allows this to be assigned to an individual or working group.

More complex implementations may prefer wider solutions which support wider product management conceptual groups such as Epics and Features.

Key characteristics of a Backlog Work Management system include:

 - Owned and accessed by the Engineering Team
 - Ability to capture a work item (typically as a "User Story" or as an issue)
 - Ability to assign the work item to a party or individual, as necessary
 - Ability to track progress of the item
 - Ability to schedule when the work will take place (this may be a named iteration or calendar date)

There are many free or commercial tools for managing [iterative delivery processes](/cloudmarque/operations/ceremony/). Advanced solutions offer far higher configurability and reporting capabilities which should be evaluated in the context of your organisation.

Bear in mind the importance of sustained data quality and consistency to meet any reporting requirements: backlog and work item tracking is only as good as the data available, and data quality established during the initial backlog population must be sustained over the long term. It's easy to over-commit planning resource to populate every available field in a work item, so evaluate your needs carefully.

Potential tools for your backlog include:

 - Azure DevOps
 - GitHub Projects
 - Microsoft Planner

Consider also whether it is important for your Engineering Team to have an integrated solution for backlog work item management and deployment pipeline CI/CD, which can simplify some management tasks via a common interface.

## Logs
A cloud [Logging workload](/cloudmarque/architecture/core/monitoring.html) is provided as part of the [Core Building Block](/cloudmarque/architecture/core/) in the Cloudmarque Reference Architecture.

This system captures the events that have taken place in the cloud environment and enables them to be queried when unexpected behaviour is detected, which can then be routed to the Service Desk team. Please refer to the documentation for more information.