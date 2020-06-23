---
layout: default
title: Reference Architecture
summary: Explore the elements of the Cloudmarque Reference Architecture, and understand the design principles that lie behind it.
jumbotron: ref-arch2
use_nav: false
scripts:
  post:
   - https://d3js.org/d3.v4.min.js
   - /assets/js/offset.min.js
   - /assets/js/polylabel.js
   - /assets/js/ref-arch.js
---
## Getting around
The reference architecture is arranged in a three-tier hierarchy. Each component has a defined role and characteristics, providing "services" to other components. These services become more granular and specific deeper into the hierarchy.

<div class="media pb-4">
    <img class="mr-3" src="/assets/images/headers/ref-arch-outline.svg" alt="Generic placeholder image" height="64px" width="64px">
    <div class="media-body">
        <h5 class="mt-0">Cloudmarque Reference Architecture</h5>
        <p>
            The "root" of the hierarchy is the Cloud Reference Architecture itself. This may be applied universally to all cloud deployments in an organisation, or to individual environments within a cloud estate (for example aligned to business units, quality assurance, or apps).
        </p>
        <p>
            <em>The Reference Architecture is comprised of multiple:</em>
        </p>
    </div>
</div>
<div class="media mt-3">
    <div class="pr-3">
        <img src="/assets/images/headers/arch-devops.svg" alt="Generic placeholder image" height="64px" width="64px">
    </div>
    <div class="media-body">
        <h5 class="mt-0">Building Blocks</h5>
        <p>
            A <em>Building Block</em> is an architectural subdomain, and contains solution templates for common concerns in that subdomain. They are high-level logical groups that contain related capabilities of a cloud estate. There are currently six building blocks:
            <ul>
                {% for block in site.data.blocks %}
                <li><a href="{{ block.docs_url}}">{{ block.name }}</a></li>
                {% endfor %}
            </ul>
            <p class="pt-4">
                <em>Each Building Block is comprised of multiple:</em>
            </p>
        </p>
    </div>
</div>
<div class="media mt-3">
    <div class="pr-3">
        <img src="/assets/images/headers/stack-generic-color.svg" alt="Generic placeholder image" height="64px" width="64px">
    </div>
    <div class="media-body">
        <h5 class="mt-0">Components</h5>
        An architecture <em>component</em> is a collection of resources brought together to support a specific workload. This might be a compute workload such as a website, or an operational workload relating to maintenance activities. Each Stack is accompanied by cloud-specific tooling to accelerate management activities.
    </div>
</div>
