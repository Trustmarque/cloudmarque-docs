---
title: Code
summary: A fundamental part of delivery competence is creating the space and environment for producing quality code output.
competencyNavigator:
  previous: 
    name: Plan
    link: /cloudmarque/operations/competencies/plan.html
  next: 
    name: Continuous Integration
    link: /cloudmarque/operations/competencies/ci.html
books:
 - name: "Refactoring: Improving the Design of Existing Code"
   authors: Martin Fowler
   image: /assets/images/competencies/books/refactoring-code.jpg
   link: https://www.amazon.co.uk/Refactoring-Improving-Existing-Addison-Wesley-Signature/dp/0134757599/
   synopsis: |
     Learn about the art of refactoring code from one of the foremost authorities on software development. This
     is a great introduction for those who aren't familiar with refactoring code and who want to understand what
     clean, functional code looks like.
---
{% include competencies/flow.html navigator=page.competencyNavigator %}

While "good code" can be subjective, it is useful to think about what "ideal" code practices are and work backwards to understand which practises are needed in your organisation's context. This overview provides guidance for assessing and developing team competency as they seek to produce "better" code.

> "Any fool can write code that a computer can understand. Good programmers write code that humans can understand." - Martin Fowler

## Objectives
Ideal code should have the following characteristics:

 - ### Maintainable
   It should be possible to confidently change the code without undue concern for which developer makes the change or how they will do it. This ensures the wider change capability is resilient: any developer can make the change, and tools are in place to facilitate the change.

 - ### Stable
   It should be possible to confidently change the code without introducing new errors, issues, or security vulnerabilities. This helps to make change time more predictable, and minimises time spent in quality control cycles.

 - ### Appropriate
   Code changes should be tailored to the problem being solved, and not over- or under-engineered. While part of the responsiblity for an appropriate solution lies in the [planning stage](/cloudmarque/operations/competencies/plan.html), there must be commensurate attention to coding competency to ensure that implemented solutions match the expected design.

## Developing competency
To achieve the objectives outlined above, consider the following suggestions:

 1. ### Deploy collaboration tools
    Establish communication tools for the team. This may be a [Microsoft Teams Team](https://docs.microsoft.com/en-us/microsoftteams/get-started-with-teams-create-your-first-teams-and-channels)), a [Slack channel](https://slack.com/intl/en-gb/help/articles/201402297-Create-a-channel), [Gitter Community](https://gitter.zendesk.com/hc/en-us/articles/200178951-Gitter-communities-and-rooms), or other similar collaboration tooling.

    [Persistent chat](https://en.wikipedia.org/wiki/Persistent_Chat) is a key feature which enables participants to easily contribute to ongoing conversations and then "catch up" on latest communications. This is particularly useful in situations where collaborators work different shifts, work in different time zones, or return from sickness and annual leave.

    **Maturity indicators**
     - [X] Communication tooling used frequently by all members of delivery teams
     - [X] Automated "bot" notifications from CI/CD or other systems
     - [X] Team members "chip in" to conversations as necessary

 2. ### Get people talking
    Cross-discipline discussions help team members to understand the challenges and complexities of complementary delivery roles, identifying inefficiencies and addressing potential issues with minimal waste. Organise [appropriate team ceremony](/cloudmarque/operations/ceremony/) to ensure all team members share the same vision and delivery priorities.

    **Maturity indicators**
     - [X] Regular diarised delivery meetings
     - [X] Good meeting attendance with contribution from all attendees
     - [X] Issues are identified early, often through meeting discussions, and not through later quality control processes

 3. ### Repeatable development environments
    Alongside environments for delivery of a system under development should be the development environments themselves. These are the desktop environments where developer tooling is installed, including IDEs, SDKs, and local servers.

    Being able to reliably create these environments is key to being able to respond to change, particularly where delivery resources are moved between projects and need to minimise "context switching" time (the time for a resource to end a task in one delivery and begin a task in a new one). Likewise, securing development environments with appropriate secret management systems helps to establish secure app development behaviours which flow onward through the delivery journey.

    **Maturity indicators**
     - [X] Developer desktop provision is documented, scripted, or automated
     - [X] Clear secret management processes
     - [X] Consistent tooling across development team (same IDE, framework, and SDK versions)

 4. ### Enabling isolated execution
    Software is often dependent on external systems to deliver key functionality which then may be incorporated into development and test environments. Mock frameworks allow these external dependencies to be replaced with lighter, simpler dependencies which allow software under development to be executed in isolation, without these dependencies in place. While mocking data, relationships, and security boundaries can be difficult, this is often preferable to maintaining these alongside an external system which defines them, and which may be impractical to deploy to development environments.

    For complex systems it is not viable to have all dependent systems available in a development environment, and abstractions alongside mocking frameworks must be used to validate system functionality.

    **Maturity indicators**
     - [X] Systems under development are not reliant on external systems or data to run and test
     - [X] Software abstractions are in place to enable mocked dependencies

 5. ### Early code validation
    Perform code validation as early as practically possible in the delivery lifecycle to help developers maintain code quality. Depending on the technology being used, it may be possible to fail builds or prevent commits where:

     - Code style conventions are not met
     - Documentation is missing or incomplete
     - Analysis tools (security, performance, complexity) identify issues
     - Commit reasons are provided but do not meet a required format
     
    The earlier these are caught, the more efficient the team will be delivering value.

    **Maturity indicators**
     - [X] Code style/convention/hygiene checks are run prior to code commits
     - [X] Documentation is automatically generated from validated code comments
     - [X] Developers cannot identify who wrote code based on style and formatting
     - [X] Release notes are automatically generated

{% include competencies/flow.html navigator=page.competencyNavigator %}
{% include competencies/books.html books=page.books %}