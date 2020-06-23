---
title: Building a DevOps Team
summary: Find out what team structures are the best fit for your organisation and understand how they work together.
---
While a broad term, _DevOps_ refers to the bringing together of two traditionally separate technology functions: _Development_ and _Operations_. In the past, the responsibilities and activities of these teams have been separate:

 * **Development** - Creating new technology features in a product or environment.
 * **Operations** - Maintaining stable technology delivery.

This division often leads to competing priorities, with Development Teams seeking to create a rapid pace of change and Operational Teams aiming to limit disruption to stable services. By bringing these disciplines together into a single team, both stability and change can be delivered collaboratively.

_DevOps_ as a term can therefore refer to:

 * The culture and working practises of unified Dev and Ops teams, and the removal of the traditional barriers between siloed teams.
 * The automated [Continuous Integration]() and [Continuous Delivery]() competencies put in place by a _DevOps_ team.
 * The Microsoft work management product, [Azure DevOps](https://azure.microsoft.com/en-us/services/devops/).

There are several ways to bring Development and Operational capabilities together:

 * ### Unified DevOps Team
   The goal of a DevOps team is to bring together both development and operational capability in a single collaborative group, using a unified work management methodology. Guidance through this operating guide assumes that this is the target DevOps model.

 * ### SRE Team
   Google use the concept of Site Reliability Engineering (SRE) teams to deliver DevOps. This involves a quality-gate approval from development teams in order to accept change into service, but can become an anti-pattern involving 

 * ### Guild-based DevOps Team
   A "guild" describes a technology capability which cuts across members of multiple Developement and Operational Teams. Guilds could be organised around technologies such as BI, Databases, Containers, or Web APIs. If your organisation has a major investment in a specialist technology, you may want to create DevOps teams unifying Development and Operations _for a given technology_ (see also [Type 8 and Type 9 teams](https://web.devopstopologies.com)).

 * ### Transitional
   Finally, if there is considerable exploration and education required to adopt a Unified DevOps approach, a temporary team can be created to facilitate the transition. The role of this team is to:

    * Champion DevOps practises and translate ideas between traditional development and operational teams.
    * Form a stepping-stone to one of the models described above, by either:
       * Facilitating and nurturing the creation of new processes which unify the Development and Operational teams, or
       * By growing to _become_ the new DevOps capability, having new team members transferred into the team from Development or Operations until only the new team remains.
    It's a good idea to make it explicitly clear which transitional approach the team is taking.

_A deeper analysis of DevOps models can be reviewed at [DevOpsTopologies.com](https://web.devopstopologies.com)._

## Engineering
The Engineering Team work to deliver cloud management tooling via an [Iterative Delivery Process](/cloudmarque/operations/ceremony/). Team responsibilities include:

 - Carry out ceremony to develop and publish new cloud tooling in service of the organisation
 - Document tooling and processes for the benefit of the Service Desk Team
 - Respond to issue escalations from the Service Desk Team on behalf of customers

The team will require the following systems and software:

 - Development tools
 - Source code repositories
 - [Tooling distribution](/cloudmarque/operations/adoption/systems.html) and versioning system
 - A [Knowledge Base](/cloudmarque/operations/adoption/systems.html#knowledge-base) for knowledge transfer to the Service Desk team

## Service Desk
The Service Desk is an event-driven team who manage work items tracked in an [ITSM tool](/cloudmarque/operations/adoption/systems.html#itsm) according to target service levels, typically identified by service type and priority. The Service Desk requires a range of stable communication platforms to interact with service consumers (typically email, phone, web, IM). They are responsible for:

 - Investigating and triaging raised issues to identify the correct service response and priority
 - Performing remedial activities where these are appropriately documented
 - Regularly communicating the incident and request status to relevant parties (proactively and reactively)
 - Routing incidents and requests onward to specialist teams for fulfilment


The team will require the following systems and software:

 - [ITSM tool](/cloudmarque/operations/adoption/systems.html#itsm) for work item tracking (ideally specialist teams should also have access to the tool)
 - A [Knowledge Base](/cloudmarque/operations/adoption/systems.html#knowledge-base) documenting incident handling procedures
 - [Deployment Pipelines](/cloudmarque/operations/adoption/systems.html#pipelines) configured to access and update any managed cloud environments