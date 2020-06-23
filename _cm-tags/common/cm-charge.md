---
title: cm-charge
summary: Tags a resource with a cost center for billing management.
category: Global
types: String
description: |
   Supports complex billing scenarios by indicating that the costs for the tagged resource
   should be aggregated against this identifier. Only a single "Bill To" reference can be tagged
   against a resource.

   Hierarchical billing can be supported using Bill To values following an agreed convention
   such as `root.parent.child.leaf`, and performing custom processing on the resulting
   usage data from a cloud bill.
formats: 
 - token: "TEXT"
   components:
    - key: "TEXT"
      type: String
      description: Use any organisational reference or canonical name to assign charges.
   examples:
    - value: "HR"
      description: Assign charges for this resource to the HR department
    - value: "123-45-6"
      description: Assign charges for this resource to the specified account number
 - token: "ROOT.BRANCH.LEAF"
   examples:
    - value: "ACME.HR.RECRUITMENT"
      description: Assign charges for this resource to "Recruitment" in the ACME HR department
---
{% include tag-details.html tag=page %}