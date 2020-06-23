---
title: Continuous Deployment/Delivery
summary: Increase automation to provide a seamless and reliable "path to live" once code is complete, tested, and ready to deploy.
competencyNavigator:
  previous: 
    name: Continuous Integration
    link: /cloudmarque/operations/competencies/ci.html
  next: 
    name: Operate
    link: /cloudmarque/operations/competencies/operate.html
books:
 - name: Continuous Delivery
   authors: Jez Humble, David Farley
   image: /assets/images/competencies/books/cd-cd.jpg
   link: https://www.amazon.co.uk/dp/0321601912/
   synopsis: |
     Once your software is ready to release to users it must be deployed. This book explains how to de-risk and efficiently manage
     your deployment pipeline to make releasing software as simple as possible.
---
{% include competencies/flow.html navigator=page.competencyNavigator %}

_Continuous Delivery_ is an extension of Continuous Integration. Where Continuous Integration ends with a tested, packaged product, Continuous Delivery takes that product and puts it into an automated release process. The end result of Continuous Integration and Delivery is the ability to take a product all the way from code to a production environment at the push of a button.

_Continuous Deployment_ takes this concept further still, removing the requirement to "push a button" to release. Every deployment which passes integration successfully is deployed automatically to the live environment.

Both practises represent the transition from development of a system to its operation. See [Teams](/cloudmarque/operations/adoption/teams.html) for a description of how these responsibilities can be distributed in unified teams.

> "We don't have a release manager and there are no set weekly deploys. Developers and designers are responsible for shipping new stuff themselves as soon as it's ready." - [GitHub Blog](https://github.blog/2012-08-29-deploying-at-github/)

## Objectives
Ideal continuous deployment processes should have the following characteristics:

 - ### Minimal human intervention
   Minimise the amount of human effort required to deploy a product to a live environment. This ensures that personnel are working on value-add activities rather than repetitive "overhead" costs. Minimising human interaction also reduces a source of error, as people are typically poor at repeating complex tasks.

 - ### Repeatable deployments
   Deployments should be reliable, so that personnel are not worried about releases which have to be meticulously planned and executed. Deployments should become predictable, with high confidence and low risk.

 - ### Timeless deployments
   The timing of deployments should matter less as organisations develop competencies in this space. Product technology decisions can be made to reduce dependencies or ensure data migrations do not interrupt normal processing. With these in place concepts such as release windows can be removed and deployments made at any time of day.

## Developing competency
To achieve the objectives outlined above, consider the following suggestions:

 1. ### Deployment technology
    Establish the technology (or technologies) to be used for CD. This may be an extension of your existing
    CI infrastructure, for example [Azure DevOps Pipelines](https://docs.microsoft.com/en-us/azure/devops/pipelines/get-started/what-is-azure-pipelines?view=azure-devops) or [GitHub Actions](https://help.github.com/en/actions)

    **Maturity indicators**
     - [X] CD processes are automatically triggered from CI processes
     - [X] Sequential release of deployment packages through staging environments to production
     - [X] Use of deployment patterns such as [blue-green deployments](https://martinfowler.com/bliki/BlueGreenDeployment.html)

 2. ### Robust QA and approval processes
    As CD approaches are an extension of CI, it is expected that CI processes (and particularly automated testing regimes) are already mature. This is particularly true for Continuous Deployment practises where the output of CI is automatically released to live.

    **Maturity indicators**
     - [X] Low number of deployments to live environments found to have errors
     - [X] Automated release approval processes (Continuous Delivery may involve a manual approval step or deployment windows)
     - [X] Roll _forward_ (i.e. create a new release) when issues occur in live rather than rolling _back_

 3. ### Automatic notifications
    Keeping relevant parties informed of releases is an important part of release practise. This may take the form of automatically
    created release notes, emails to customers, or IM-based notifications to internal teams.

    **Maturity indicators**
     - [X] Agreed communication platform and channels
     - [X] Release notifications describing change and release information are created and distributed automatically
     - [X] Accessible user-facing release history and details

 4. ### Embedded monitoring
    In rare cases that errors are not caught by CI processes, it is important to have robust monitoring software in place to detect any issues in live environments once the release process is complete.

    **Maturity indicators**
     - [X] Ability to identify the build/release associated with any logged failures
     - [X] All errors are logged
     - [X] Wider performance monitoring and dependency monitoring tools are in place
     - [X] Failures are detected swiftly, and routed efficiently to development teams

 5. ### Deployment design
    Technology selection and coding patterns are put in place to support CD processes.

    **Maturity indicators**
     - [X] Use of software patterns such as [feature toggles](https://www.martinfowler.com/articles/feature-toggles.html)
     - [X] Systems are designed to minimise or remove downtime caused by data migrations
     - [X] Data backup and restore processes are aligned to support disaster recovery scenarios

{% include competencies/flow.html navigator=page.competencyNavigator %}
{% include competencies/books.html books=page.books %}