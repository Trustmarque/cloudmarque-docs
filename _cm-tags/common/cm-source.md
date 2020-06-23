---
title: cm-source
summary: Tags a resource with information that can be used to trace its origins.
category: Global
types: JArray
description: |
   Designed to help manage environments by documenting where the resource came from. This can
   assist in resolving versioning issues or when upgrading to newer scripts, as it provides
   a basis for comparing the source which originally defined a resource with an upgraded version.

   This information is picked up from the [Cloudmarque Azure context](/cloudmarque/reference/commands/set-cmazcontext.html) and is set on resources when
   deploying cloud resources.
formats: 
 - token: "[ TOOLING, REPOSITORY, PIPELINE, RELEASE, DATE ]"
   components:
    - key: "TOOLING"
      type: String
      description: Any named version of a versioned cloud deployment tool (or collection of tools)
    - key: "REPOSITORY"
      type: String
      description: A reference to the source repository
    - key: "PIPELINE"
      type: String
      description: The name of the source pipeline
    - key: "RELEASE"
      type: String
      description: The name of the release
    - key: "DATE"
      type: DateTime
      description: An ISO8601 formatted reference to the deployment time
   examples:
    - value: "[\"Cloudmarque.Azure v0.93 (PowerShell)\", \"Azure DevOps (Acme)\", \"IaaS Web\", \"Release 1202\", \"2020-01-01T23:53:01Z\"]"
      description: |
        Indicates that the resource was provisioned by Cloudmarque version 0.93, from the Azure DevOps Acme repository,
        using the IaaS Web release pipeline, number 1202, on the first of January 2020 (at around 7 minutes to midnight)
---
{% include tag-details.html tag=page %}