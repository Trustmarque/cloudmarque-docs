---
title: Tagging
summary: Cloudmarque operational automation is powered by the ability to tag cloud resources with management metadata.
tags: tags, automation, meta
---
{% if site.data.tags.meta.prefix %}
All Cloudmarque tags are prefixed with `{{ site.data.tags.meta.prefix }}` to avoid conflicts with other tagging conventions. To avoid future conflicts, do not prefix your tags with `{{ site.data.tags.meta.prefix }}`.
{% endif %}

Tagging capabilities vary between cloud platforms. Cloudmarque is designed to operate within the tagging capabilities of Azure and AWS.

## Standard tags
The following tags may be applied to any resource in a cloud environment. 

{% include tag-table.html prefix=site.data.tags.meta.prefix separator=site.data.tags.meta.separator tags=site.cm-tags %}