---
title: Ceremony
summary: Establish working patterns and practises for Engineering Teams, setting a delivery and improvement cadence for cloud systems.
---
Cloudmarque-aligned Engineering Teams are designed to follow Agile working practises[^1], operating on a repeating, fixed-length work cycle called an _Iteration_. An iteration incorporates various meetings (or _ceremonies_) which take place at specific times in the iteration.

One of the first tasks for your Engineering Team is to set an iteration duration and agree how ceremony should be implemented.

## Choosing an iteration duration
Initial factors to consider include:

 1. ### Multiple teams
    If your organisation expects to run multiple Engineering Teams, consider offsetting iteration cycles. You might want to do this to:
     * ensure that team ceremonies are not competing for meeting rooms
     * manage delivery dependencies between teams
     * offset releases (where legal or compliance issues prevent "release when ready")


 2. ### Duration
    Iteration durations range from one to four weeks, and choice of duration depends on a range of desired characteristics and wider organisational context.
     * The main factor when deciding iteration duration is uncertainty. In extremely volatile environments where processes and approaches have to be continually revised, shorter iterations mean less waste when an approach does not work and has to be thrown away. Longer iterations work better when goals are fixed and dependencies are well-understood (or they have been done many times).

     * Try to keep ceremony duration appropriate to the length of the iteration. The ratio of ceremony to "delivery" time shouldn't be a factor in avoiding shorter iterations.

     * One of the main focuses of the Engineering Team should be reducing the overhead of running a cycle. Alongside ceremony, the "path to live" of packaging, test, and release represents significant cycle overhead which can be more obvious in smaller iteration durations, and focus the team on improving automation in these areas.

## Are iterations required?
A pure Kanban methodology with no iterations can be an effective way to run a reactive Engineering team. Proactive innovation and improvement typically require planning for long-term change, which iterative Agile ceremony outlined in this Operating Guide supports. Similar processes can be implemented via Kanban lifecycle reviews[^2].

## Ceremony
During an iteration the Engineering Team should establish five regular ceremonies:

 1. ### [Refinement](/cloudmarque/operations/ceremony/refinement.html)
    The Engineering Team and their Product Owner together build, review, and prioritise a backlog of work prior to the start of an iteration.
 
 2. ### [Planning](/cloudmarque/operations/ceremony/planning.html)
    At the start of an iteration, the Engineering Team plan and commit to work items to be delivered over the course of the iteration duration.

 3. ### [Daily Standup](/cloudmarque/operations/ceremony/daily.html)
    A short, regular team conversation to share progress and remove blocking dependencies.

 4. ### [Team Sync](/cloudmarque/operations/ceremony/sync.html)
    Inter-team forum for resolving delivery dependencies across a wider engineering programme.

 5. ### [Retrospective](/cloudmarque/operations/ceremony/retrospective.html)
    The team takes the opportunity to review delivery performance through the past sprint, identifying process optimisations, and addressing productivity issues.

---
**_References_**

[^1]: For in-depth discussion of Agile practises, refer to the [Agile Alliance](https://www.agilealliance.org/glossary/iterative-development/).
[^2]: Kanban ceremony is comprised of scheduled reviews, which have many similarities to the ceremonies of Agile. The [Kanban](https://www.agilealliance.org/glossary/kanban/) descriptions outlined on the Agile Alliance site provide a comprehensive overview.