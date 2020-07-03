---
title: Learn
summary: Work with your teams to better reflect on success and failure, developing a no-blame culture that adapts and overcomes issues.
competencyNavigator:
  previous: 
    name: Monitor
    link: /cloudmarque/operations/competencies/monitor.html
  next: 
    name: Innovate
    link: /cloudmarque/operations/competencies/innovate.html
books:
 - name: Black Box Thinking
   authors: Matthew Syed
   image: /assets/images/competencies/books/black-box-learn.jpg
   link: https://www.amazon.co.uk/dp/B00PW634YQ/
   synopsis: |
     In this engaging read, Matthew Syed explains how the ability to challenge assumptions and perform candid reviews of 
     failure is an essential part of the learning process.
---
{% include competencies/flow.html navigator=page.competencyNavigator %}

Learning requires frank and honest assessment of both success and failure. Of the two, learning from failure is often the most difficult as it can be bound up with perception of personal identity, professional reputation, and individual competence. These emotive subjects can drive conflict if not managed properly.

Like many other competencies described in this document, developing this competence relies on creating an open and honest culture. Critical to the "learning" competence is encouraging a no-blame culture.

> "Your most unhappy customers are your greatest source of learning." - Bill Gates

## Objectives
Ideal continuous integration processes should have the following characteristics:

 - ### Mistakes are not repeated
   It is inevitable that failures will occur as part of a delivery process; learning competency should be developed to ensure that those mistakes are not repeated.

 - ### Impact of failure is minimised
   The learning process involves continual exploration and mitigation of risk. If failure is unavoidable, it is often possible to instead [minimise the impact of failure](https://en.wikipedia.org/wiki/Chaos_engineering). Effective teams are able to quantify and minimise risk by adapting to the changes they perceive in their environment, and they accomplish this within the iterative improvement cycle.

 - ### Shared understanding is developed
   The characteristics of the problem and solution space should be better understood by the delivery team as time progresses. It is important to recognise and encourage the formation and recording of this knowledge as teams and their focus inevitably change over time, and accrued collective wisdom needs to be preserved.

## Developing competency
To achieve the objectives outlined above, consider the following suggestions:

 1. ### No-blame culture
    After following a failure analysis process (such as the [Five Whys](https://en.wikipedia.org/wiki/Five_whys) technique) the result should be a root cause of process or policy, rather than people. This helps to depersonalise failure and enables team members to talk candidly about causes and solutions.

    For example, if a user forgot to make a critical update to some software then the process could be changed to include timed warnings, additional checks, new regular training, and/or future automation of the process.

    **Maturity indicators**
     - [X] Root cause analysis takes place as part of [retrospective ceremony](/cloudmarque/operations/ceremony/retrospective.html)
     - [X] Failures of process and policy are regularly identified and improved
     - [X] Individuals freely own up to mistakes and join in discussions about how they can be addressed

 2. ### Language changes
    Avoid personalising ideas ("his idea/her idea") and instead invoke more inclusive terms ("our suggestion"). Consider making more explicit use of scientific language like _hypotheses_: "we have a hypothesis that performance will improve if we rewrite the user interface in COBOL".

    Using the term "hypothesis" immediately sets a cultural expectation that the hypothesis should be proven or disproven, which is a useful work item that can be creatively addressed (see also the [Innovation](/cloudmarque/operations/competencies/innovate.html) competency) and evaluated.

    **Maturity indicators**
     - [X] Work items often include hypotheses
     - [X] Metrics are related to a hypothesis and recorded to feed back in to the learning process
     - [X] Personalisation of ideas is avoided and group ownership is adopted


 3. ### Documented learning
    Encourage learning points to be recorded. There are many different potential repositories for this.

    **Maturity indicators**
     - [X] Actions from retrospectives are documented and archived
     - [X] A knowledge base (this could simply be a document) is maintained with key learnings from the team
     - [X] Decisions are logged, recorded, and "archived but accessible"
     - [X] New team members are introduced to the wisdom that the team has developed and recorded

{% include competencies/flow.html navigator=page.competencyNavigator %}
{% include competencies/books.html books=page.books %}