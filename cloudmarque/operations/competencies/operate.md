---
title: Operate
summary: Enhance your operational capability, developing efficient processes for responsive and timely handling of service requests and issues.
competencyNavigator:
  previous: 
    name: Continuous Deployment
    link: /cloudmarque/operations/competencies/cd.html
  next: 
    name: Monitor
    link: /cloudmarque/operations/competencies/monitor.html
books:
 - name: The Site Reliability Workbook
   authors: Betsy Beyer, Niall Murphy, David Rensin, Kent Kawahara, Stephen Thorne
   image: /assets/images/competencies/books/sre-operate.jpg
   link: https://www.amazon.co.uk/Site-Reliability-Workbook-Practical-Implement/dp/1492029505/
   synopsis: |
     Google's "Site Reliability Engineering" (SRE) philosophy describes their approach to the software lifecycle, and this book provides
     examples for putting that theory into practise with new or existing teams and technologies.
---
{% include competencies/flow.html navigator=page.competencyNavigator %}

Operational capability incorporates the ability to handle service requests and appropriately escalate issues detected by users. High levels of competence in this area can be achieved by following the [adoption advice](/cloudmarque/operations/adoption/) described in this guide. Operational excellence involves bringing together a Service Desk Team with IT Service Management (ITSM) systems to efficiently handle queries, failures, and service requests.

Operational competence and Monitoring capability both involve effective handling of live system issues. Operational competence addresses user-instigated requests, while monitoring deals with proactively detected failures. Both require tight co-ordination and clear communication between teams.

> "It is the long history of humankind (and animal kind, too) that those who learned to collaborate and improvise most effectively have prevailed." – Charles Darwin

## Objectives
Ideal operational capability should have the following characteristics:

 - ### Repeatable
   Operational processes should be repeatable and consistently achieve a desired outcome.

 - ### Clear
   Participants in any operational process should understand their role in any workflow and the state of any items they are dealing with in that workflow. They should also have clear objectives for moving items through the workflow in terms of activity time, quality, and outcomes.

 - ### Complete
   Operational processes typically involve a number of people performing work in sequence to achieve some objective. 

## Developing competency
To achieve the objectives outlined above, consider the following suggestions:

 1. ### Leverage technology
    Ensure an IT Service Management tool is in place to store tasks that are being worked on. These range in capability and complexity (and therefore, cost), but basic implementations can be delivered cheaply. All service personnel should use this system to track work items and hand them off between teams.

    **Maturity indicators**
     - [X] ITSM tool deployed and in place
     - [X] ITSM tool has multiple communication channel integrations (web, phone, email)
     - [X] ITSM service requests can be categorised by priority, severity, and an appropriate organisational taxonomy

 2. ### Set Service Level Objectives
    Define the time periods in which service activities will take place. This may include commitments to response and incident resolution times, applicable working hours, and scope of services.

    **Maturity indicators**
     - [X] SLOs are defined and communicated to service delivery personnel and end-users
     - [X] Established Service Desk shifts to cover SLO working hour provisions, annual leave, and sickness
     - [X] SLOs are tracked, measured, and intentionally improved

 3. ### Automate
    Find ways to automate common workflows for issues and service requests.

    **Maturity indicators**
     - [X] Prepare standard responses with user guides for troubleshooting common issues
     - [X] Develop simple routing heuristics, for example routing queries containing specific words to relevant teams automatically
     - [X] Ensure all user-facing responses have standard footers containing general contact and process guidance
     - [X] Develop systems to capture and retain relevant additional details for specialist service requests
     - [X] Anonymise data after an appropriate time period to prevent privacy breaches

{% include competencies/flow.html navigator=page.competencyNavigator %}
{% include competencies/books.html books=page.books %}