---
title: Monitor
summary: Build your capability to track what matters to your organisation, and contextualise metrics to understand the customer narratives behind them.
competencyNavigator:
  previous: 
    name: Operate
    link: /cloudmarque/operations/competencies/operate.html
  next: 
    name: Learn
    link: /cloudmarque/operations/competencies/learn.html
books:
 - name: Lean Analytics
   authors: Alistair Croll, Benjamin Yoskovitz
   image: /assets/images/competencies/books/lean-analytics-monitor.jpg
   link: https://www.amazon.co.uk/Lean-Analytics-Better-Startup-OReilly/dp/1449335675
   synopsis: |
     Develop a data-driven mindset to product improvement with practical examples of the use and abuse of metrics in different organisational
     scenarios. Useful from a business and product management perspective on monitoring as part of a build/measure/learn cycle.
---
{% include competencies/flow.html navigator=page.competencyNavigator %}

Monitoring competency involves identifying system metrics and logs, configuring thresholds and alerts, and retaining data for post-event triage and analysis. In addition, user behaviours and metrics may be tracked to help inform future delivery efforts. Metrics and alerts may be combined and used to identify unusual events which could indicate security breaches.

Building competence in monitoring involves regular review of the usefulness of metrics being monitored, suitability of alert thresholds, and lifecycle management of retained data.

> "If the metrics you are looking at aren't useful in optimizing your strategy - stop looking at them." - Mark Twain

## Objectives
Ideal monitoring capability should have the following characteristics:

 - ### Provide insights
   Monitored metrics should inform prioritisation of features. This may require the development of support for custom metrics in a system.

 - ### Detect failure
   Monitoring is the eyes and ears of your deployed environments, constantly recording the health of your systems at a rate that no manual process ever could. It is important for this capability to reliably indicate unexpected conditions that need to be remediated. Reliability means avoidance of "false positives" (where systems are incorrectly reported as healthy), _and_ "false negatives" (where systems are incorrectly reported as unhealthy).

 - ### Allow root cause analysis
   Retained logs and metrics should allow retrospective analysis of failure events. This learning activity helps increase system stability over the long-term.

## Developing competency
To achieve the objectives outlined above, consider the following suggestions:

 1. ### Tailored alert thresholds
    Tailoring monitoring systems to reduce noise is essential, as a "noisy" alert system will result in "alert fatigue" of Service Desk personnel. This is an incredibly important activity to focus on as part of continual improvement processes, as time is wasted chasing irrelevant warnings while service-impacting failures are lost in the sea of alerts.

    **Maturity indicators**
     - [X] All alerts are followed up: no alerts are routinely ignored because they are "not relevant"
     - [X] Alerts deemed irrelevant have their alert thresholds or criteria changed, or they are removed
     - [X] Alerts are tailored on a per-system basis: 90% memory usage may be expected for some workloads, but an indication of failure in others

 2. ### Intentional data retention
    Be proactive about deciding what data is logged and how long it is retained. Change systems to meet your requirements, don't just accept the defaults you are provided.

    **Maturity indicators**
     - [X] Log and metric data is securely destroyed after a defined time period
     - [X] Log data does not include sensitive information
     - [X] Metrics are tracked on an appropriate basis (CPU may be appropriate to track every 10 seconds, but remaining disk space may be recorded every hour)

 3. ### Onward processing of metrics
    Metrics are utilised to inform wider service delivery, and potentially incorporated into new data sets to inform wider organisational decisions.

    **Maturity indicators**
     - [X] Log and metric data is anonymised, sampled, and routed to organisational business intelligence tools
     - [X] Log and metric data is consumed by SIEM tools
     - [X] Log and metric data is used to understand whether SLA/SLOs have been met

{% include competencies/flow.html navigator=page.competencyNavigator %}
{% include competencies/books.html books=page.books %}