---
title: Iterative Delivery Principles
summary: Take a look "behind the curtain" at the theory of iterative delivery models, in order to better apply them to your own context.
---
When designing delivery teams it is important to understand why Iterative Delivery models work, as this helps tailor them to individual organisational needs. This page describes some of the principles which underpin Iterative Delivery. 

Understanding this theory provides context to Agile structures, allowing implementors to understand why particular [ceremony](/cloudmarque/operations/ceremony/) works, and to better tailor it to specific organisational contexts.

## Fail fast
Time spent delivering the wrong thing is wasted investment. One of the key benefits of Iterative Delivery models is that they quickly find and eliminate waste. For example:

 - breaking down work into smaller deliverable items, meaning less investment before capitalising on new opportunities and mitigating unexpected risks

 - regularly re-assessing the delivery landscape and responding to shifting business priorities

 - increasing cross-discipline team communication to minimise technical conflict and maximise quality: fewer issues handled more efficiently means less waste

When assessing the effectiveness of your Iterative Delivery implementation, some key questions to consider are:

 1. What wasted effort is this process detecting and eliminating?
 2. Will this practise be more effective if it were shorter, longer, or performed more or less frequently?
 3. Is the detail level of analysis or delivery work appropriate?
 4. Are inefficiencies being actioned and waste eliminated with the appropriate priority?

_Fail fast_ is the golden rule of Iterative Delivery: the subsequent principles in this guide are variations on this theme which target specific areas of the Iterative Delivery process.

## Reduce batch sizes
Batch size refers to the amount of work that a single iteration of a delivery cycle produces. Small batch sizes mean less waste if there is a defect with the batch; the technical approach does not work, or unforeseen problems arise.

Two factors govern the most efficient batch size:

 - **Holding cost** describes the cost of delay, or _not_ processing an item in the work batch. This incorporates a range of impacts specific to your context, for example:

    - The lost profitability of your product or service being delayed to market
    - Costs incurred from processes or systems not replaced by your delivery
    - Manual labour to compensate for features not delivered
    - Reputational damage from missed delivery expectations

Holding costs rise for larger batch sizes.

 - **Transaction cost** describes the cost of transacting, or processing the batch of work. This includes:

    - The time investment of running a delivery cycle
    - Tooling 
    - Materials, particularly including perishable or single-use items

Transaction costs typically reduce for larger batch sizes.

When these two factors are summed, the optimum batch size is shown to be the lowest point in the resulting U-curve:

![A graph showing the intersection of holding and transaction cost as a U-curve](/assets/images/ref-arch/ops-batch-size.svg)

It is usually impractical to model these costs directly, either because the cost of modelling is more than the potential efficiency savings or because compound value estimates become meaningless. As a result, these costs are best used as a rule of thumb to guide decisions around work management and team setup.

## Reduce cycle time
Having established a team with a regular work cadence it is important to identify and reduce overheads associated with running an iterative delivery cycle.

A good analogy is engine efficiency. An engine converts chemical energy to useful forward motion, or kinetic energy. However, this converstion is not 100% efficient, and some of the chemical energy is converted to "waste" energy such as heat and sound.

In a delivery cycle not all the team's efforts go into value-building activities such as writing computer code or learning how to configure and manage system behaviours. There are activities that have to be performed regularly, and these are prime candidates for investment in automation:

 - Software packaging and versioning
 - Quality controls (testing)
 - Deployment and distribution activities
 - Training and change notification processes

Investment in reduction of cycle times via automation is governed by three factors:

 1. The cost of performing the activity before and after automation (i.e. the expected savings)
 2. The failure cost of the process, which should account for both the failure rate, and the cost of rectifying errors
 3. How many times the activity is performed (per cycle), and how many cycles you expect to perform
 
Bear in mind the "hidden" costs associated with failure: reputational damage, lost business, etc. These can quickly become a much greater factor than a more simplistic measure of return on investment which only looks at time savings versus payback time.

## Factories not products
It is easy to see delivery teams as creators of a specific product or service. However, as a team moves to deliver a product or service at scale, it can be more useful to think of them as builders of a factory, rather than a product.

| Product-thinking                           | Factory-thinking                                 |
|:------------------------------------------:|:------------------------------------------------:|
| Ensure the product is defect-free          | Ensure QA processes produce defect-free products |
| Install product updates                    | Define a product update process and schedule     |
| Write product documentation                | Generate, maintain, and distribute documentation |
| Find out how many users access the product | Establish a self-service reporting dashboard     |

Investment in automation processes is only necessary once activities are repeated enough times to justify a return.

However, it's important to keep taking a step back from point-solutions that focus on solving the specific issue in front of the team to review "big picture" of why the issue is happening in the first place, and whether development of a wider factory capability would be more worthwhile.

The following misquote from Ian Fleming encapsulates this mindset:

> Once is happenstance,
> Twice is coincidence,
> The third time it's ~enemy action~ worth automating.

## Avoiding work
The cheapest and fastest processes are the ones that you don't do at all.

It is easy to slip into traditional ways of working and establish processes due to organisational inertia. Actively challenging and deconstructing such processes can yield new insights and efficiencies.

For example:

 - Are validation processes forcing an unnecessarily high level of data quality?
 - Can QA gates be changed as customers are happy to trial "beta" features in production environments, even with known errors (a.k.a "done is better than perfect")
 - Are extensive delivery reports useful, or are there a handful of key reporting metrics that stakeholders review and most of the report is not utilised?

It is important to establish context when exploring these options with a team, explaining that the team is asked to find innovative solutions outside of normal working practise, and not questioning individual professionalism or competency.

## Where next?
 - [Think about how to set up your teams](/cloudmarque/operations/adoption/teams.html)
 - [Learn about ceremony in iterative delivery](/cloudmarque/operations/ceremony/)