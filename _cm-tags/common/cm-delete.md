---
title: cm-delete
summary: Tags a resource for deletion at a specified date and time
category: Global
types: JObject
description: |
   Supports complex billing scenarios by indicating that the costs for the tagged resource
   should be aggregated against this identifier. Only a single "Bill To" reference can be tagged
   against a resource.

   The exact timing of the delete activity will depend on when the Automation job is scheduled. By
   default, this runs every hour.
formats: 
 - token: "DATETIME"
   components:
    - key: "DATETIME"
      type: DateTime
      description: A date and time in zulu form.
   examples:
    - value: "2020-01-01T00:00:00Z"
      description: Midnight on the 1st January 2020 (UTC time)
---
{% include tag-details.html tag=page %}