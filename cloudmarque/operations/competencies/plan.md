---
title: Plan
summary: Develop your ability to define scope, estimate effort, and move toward long-term strategic goals using a roadmap.
competencyNavigator:
  previous: 
    name: Innovate
    link: /cloudmarque/operations/competencies/innovate.html
  next: 
    name: Code
    link: /cloudmarque/operations/competencies/code.html
books:
 - name: "User Stories Applied"
   authors: Mike Cohn
   image: /assets/images/competencies/books/stories-plan.jpg
   link: https://www.amazon.co.uk/User-Stories-Applied-Development-Addison-Wesley/dp/0321205685/
   synopsis: |
     Central to planning is the creation of good quality requirements in the form of user stories. Mike Cohn explains both good and
     bad story writing, introducing concepts alongside practical advice and guidance.
 - name: "Principles of Product Development Flow"
   authors: Donald G. Reinertsen
   image: /assets/images/competencies/books/flow-plan.jpg
   link: https://www.amazon.co.uk/dp/B007TKU0O0/
   synopsis: |
     Understand the math behind queues, and how this affects the flow of work between systems. This foundational book is more abstract,
     but an incredibly useful guide to navigating the complex world of prioritisation, risk, and task dependencies.
---
{% include competencies/flow.html navigator=page.competencyNavigator %}

Planning competency works to increase the predictability of delivery work through regular roadmap reviews, reflection, and work estimation techniques. Key to developing this competency is creating [ceremony](/cloudmarque/operations/ceremony/) to establish a regular cadence for review.

> "Always plan ahead. It wasn’t raining when Noah built the Ark." - Richard Cushing

More traditional "waterfall" approaches often give an illusion of control by presenting an idealised view of the future. In reality most delivery scenarios have many unpredictable risks which are not identified in an early design phase, and without an iterative approach there is no effective way to control such risks. However, "waterfall" can be a good fit for repeated activities of precisely known size, scope, and low/controlled risk.

## Objectives
Ideal continuous integration processes should have the following characteristics:

 - ### Clear prioritisation
   Work items have clear prioritisation both inside and outside of delivery iterations to keep teams focussed on delivery of value. In this context, "team" includes the organisational representive (product owner) responsible for prioritising work.

 - ### Predictable commitment
   Delivery teams are able to deliver committed work within an agreed iteration period. This helps to make deliveries predictable.

 - ### Responsive to change
   Planning activities should be responsive enough to deal with changes in priorities across iterations. For volatile environments, consider using a process like Kanban to keep teams responsive to change.

 - ### "Enough" architecture
   The team should plan architectural components and frameworks to enable delivery of upcoming work items (say, over the next 2-5 iterations) without wasted redesign and refactoring effort.

## Developing competency
To achieve the objectives outlined above, consider the following suggestions:

 1. ### Establish ceremony
    Create team meetings to plan, review progress, and reflect on team success and failure. Descriptions of these meetings can be found in [ceremony guidance](/cloudmarque/operations/ceremony/) in the Operating Guide.

    **Maturity indicators**
     - [X] Regular planning meetings with relevant stakeholders
     - [X] Regular daily progress meetings with relevant stakeholders
     - [X] Regular retrospective review meetings with relevant stakeholders

 2. ### Maintain a backlog
    Identify an [information system to store your backlog](/cloudmarque/operations/adoption/systems.html#backlog). You may start with a flat list of work items, but are likely to mature toward building hierarchical collections of features and epics.

    **Maturity indicators**
     - [X] Points-based estimations for upcoming backlog items (may only be higher priority ones where a very large backlog is involved)
     - [X] Structured data supporting and grouping work items
     - [X] Dashboards showing burn up/down across different work item groupings and teams

 3. ### Practise estimating and committing to work
    Arriving at a consensus view of effort and risk involved in delivering a given work item is often an elusive and frustrating part of agile planning for new teams. A typical approach is to apply points-based estimates to work in a backlog. Teams may break work items down into hours-based tasks as part of a planning cycle to better help manage team commitment.

    Committing to deliver a set of work items during an iteration also requires a clear view of what resource is available during the iteration (annual leave, training, organisational meetings).

    See also: [Ceremony - Planning](https://docs.trustmarque.com/cloudmarque/operations/ceremony/planning.html)

    **Maturity indicators**
     - [X] Example/typical work items for different levels of points-based estimation
     - [X] All work items that the team commits to in an iteration are delivered
     - [X] Balance of architectural and business related work items in each iteration
     - [X] Clear view of resource availability in each planning meeting

{% include competencies/flow.html navigator=page.competencyNavigator %}
{% include competencies/books.html books=page.books %}