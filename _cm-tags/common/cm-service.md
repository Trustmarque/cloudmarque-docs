---
title: cm-service
summary: Tags a resource as providing a named service for dependency management.
category: Global
types: Hierarchy
description: |
   Enables the service locator pattern by marking resources as providing specific services to
   other resources. For example, a value of `core.logging.resources` indicates that the resource
   provides logging services to cloud resources. When another resource is deployed, it may be
   configured with this named dependency, which can then be usde to identify and connect to relevant
   services in the cloud environment.
formats: 
 - token: "Hierarchy"
   components:
    - key: "Service"
      type: Hierarchy
      description: A dot-segmented name identifying a service in a wider hierarchy of service types.
   examples:
    - value: "iaas.vnet.web.dmz"
      description: |
        Indicates an infrastructure VNET in a web-facing DMZ. The first two segments of the service are set
        automatically by Cloudmarque tooling, while remaining segments can be used to identify sub-resources
        in a specific implementation scenario.
---
{% include tag-details.html tag=page %}