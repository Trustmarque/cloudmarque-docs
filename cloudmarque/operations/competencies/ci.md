---
title: Continuous Integration
summary: Keep your code products always "ready to deploy" with a central code repository backed by automated build and test processes.
competencyNavigator:
  previous: 
    name: Code
    link: /cloudmarque/operations/competencies/code.html
  next: 
    name: Continuous Deployment
    link: /cloudmarque/operations/competencies/cd.html
books:
 - name: "The Devops Handbook"
   authors: Gene Kim, Patrick Debois, John Willis
   image: /assets/images/competencies/books/devops-handbook-ci.jpg
   link: https://www.amazon.co.uk/Devops-Handbook-World-Class-Reliability-Organizations/dp/1942788002/
   synopsis: |
     An accessible overview of modern DevOps practises, this book is applicable to many of the competencies described in this site. 
     Part 3's advice on deployment pipelines is particularly relevant to this section on Continuous Integration.
---
{% include competencies/flow.html navigator=page.competencyNavigator %}

_Continuous Integration_ involves taking code from a repository, then verifying and packaging it as a deployable unit. Verification can involve a range of quality controls, and typically including:

 - Ensuring that code compiles (for compiled languages)
 - Running checks on code hygiene (style, security, standards, documentation)
 - Validating application behaviour (various rounds of testing)
 - Generating and checking documentation
 - Collating and checking release notes

These steps are automated and triggered by code changes. Test failures ensure that the deployable unit is not made available for deployment.

> "I have not failed. I've just found 10,000 ways that won't work." - Thomas Edison

## Objectives
Ideal continuous integration processes should have the following characteristics:

 - ### Fail fast
   Detect issues as early as possible in the test process to flag quality issues to the development team. The faster these are found, the faster they can be remedied.

 - ### Comprehensive scope
   Continuous Integration processes should aim to incorporate a full suite of quality control measures. Typically teams may start by running unit tests to verify application behaviour at a software level, moving on to wider integration tests, deployment tests, and beyond into simulating user behaviour. These user behaviours can then be enhanced and scaled up to support performance testing.

 - ### Consistently repeatable
   A Continuous Integration process should be consistently repeatable, limiting (ideally removing) error-prone human involvement in the manual quality control measures. Automation technologies should be used to facilitate this objective.

## Developing competency
To achieve the objectives outlined above, consider the following suggestions:

 1. ### Encourage automated test capability
    Seek to automate quality control measures which are undertaken with every release. A Continuous Integration technology should be identified
    to detect change and invoke testing procedures. Make time to develop these with every new user story, feature, or technology change.

    Example technology platforms for delivering this capability include [Azure DevOps Pipelines](https://docs.microsoft.com/en-us/azure/devops/pipelines/get-started/what-is-azure-pipelines?view=azure-devops) and [GitHub Actions](https://help.github.com/en/actions), though a range of other options are available.

    **Maturity indicators**
     - [X] Unit tests are executed automatically to verify software unit behaviour
     - [X] Use of mock frameworks to simulate external dependencies without needing to deploy them
     - [X] Integration tests are executed automatically to verify software systems more holistically
     - [X] Deployment tests are executed automatically to verify packaging, upgrade, and deployment mechanisms
     - [X] User/UI tests are executed automatically to simulate user interaction with systems
     - [X] Performance tests are executed automatically to simulate large numbers of users interacting with the system

 2. ### Configure notifications
    Find ways to inform the team when a build is "broken", ideally including the names of developers whose changes caused the error. The team should focus on addressing the error and return to healthy builds before continuing to work on new features or functionality.

    Most CI technologies have integrations into a range of messaging platforms to simplify developing this competence.

    **Maturity indicators**
     - [X] "Broken build" notifications targeted to individuals or teams
     - [X] Regularly reviewed dashboard of CI pipeline health

 3. ### Supporting collateral
    While CI automates quality control measures, this should not be the first-line of problem detection for delivery teams. There should be clear standards describing the quality controls which are effectively communicated to team members. CI should be in place to verify the quality of the work already performed by developers.

    **Maturity indicators**
     - [X] Minimal number of broken builds
     - [X] Quality control standards, documentation, and/or training regimes
     - [X] On-boarding training material for new team members explaining quality control standards and processes

{% include competencies/flow.html navigator=page.competencyNavigator %}
{% include competencies/books.html books=page.books %}