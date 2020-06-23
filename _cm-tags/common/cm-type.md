---
title: cm-type
summary: Tags a resource with information that can be used to identify its type.
category: Global
types: String
description: |
   Applied to any resource which has been specialised to a particular function after
   provisioning. A disk image may be tagged as `Acme LOB Desktop, 1.1.1` to indicate
   both the type and version of its configuration.

   This tag should usually be set when the resource is created or modified, and can
   be used to manage the lifecycle of the resource. All resources with a particular
   type and version could be marked for deletion, or flagged as part of an audit
   cycle.

   There are multiple ways to address issues managing and refreshing resources.
   This can be achieved by either performing updates on the resources to upgrade
   them to a new version, or by destroying the resource completely and recreating
   a new one with an updated version.
formats: 
 - token: "NAME, MAJOR.MINOR.PATCH[-SUFFIX]"
   components:
    - key: "NAME"
      type: String
      description: |
        The name of the object type. This could be some kind of classification
        scheme ("Desktop.GB.Developer") or a simpler name ("LOB App 1").
    - key: "MAJOR"
      type: Numeric (0 or above)
      mandatory: true
      description: Major version number. Incremented when significant upgrade or migration activity is required.
    - key: "MINOR"
      type: Numeric (0 or above)
      mandatory: true
      description: Minor version number. Incremented when some small upgrade actions are required.
    - key: "PATCH"
      type: Numeric (0 or above)
      mandatory: true
      description: Patch number. No breaking changes.
    - key: "SUFFIX"
      type: Alphanumeric/slug format (lowercase)
      mandatory: false
      description: An additional release suffix.
   examples:
    - value: "Public, 1.0.0"
      description: This is version one of the "Public" resource.
    - value: "Server.Ubuntu.Web.Apache, 0.95.3-alpha-nightly"
      description: |
        Denotes a server, OS, workload, and specific middleware. This is an example
        of how a hierarchical structure could be managed. In addition, a version with
        a suffix of -alpha-nightly indicates that the type is a pre-release version
        from a nightly build source.
---
{% include tag-details.html tag=page %}