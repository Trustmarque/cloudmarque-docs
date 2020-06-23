---
title: cm-apps
summary: Tags a resource with names of the application(s) that it supports.
category: Global
types: JArray
description: |
  A list of the applications which depend on the resource. This can be used as part of operational procedures to notify application owners and users of service impacts when failures are detected.
formats: 
 - token: "[ \"AppName\" ]"
   components:
    - key: "AppName"
      type: String
      description: A named application, which likely relates to a named system in an IT asset register.
   examples:
    - value: "[ \"EmployeeRite HR\" ]"
      description: |
        Denotes that the tagged resource is a dependency of the "EmployeeRite HR" application.
    - value: "[ \"AssetLite Finance\", \"Acme BI\" ]"
      description: |
        Denotes that the tagged resource is a dependency of both the "AssetLite Finance" and "Acme BI" applications.
---
{% include tag-details.html tag=page %}