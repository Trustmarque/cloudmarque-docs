---
title: Tagging
summary: Conventions for simplified management of cloud assets, with supporting automation for common tasks based on tagged resources.
graphic: stack-core-tags
---
## Definition
Tags are not cloud resources themselves, but define custom properties to simplify management of cloud resources. Cloudmarque makes use of standard tags to manage resource behaviours and simplify management. For more information, review the [Tag reference](/cloudmarque/reference/tags/) documentation.

## Dependencies
While tags have no dependencies (they do not need to locate dependent services to be deployed), some behaviours are dependent on [scheduled automated processes](/cloudmarque/architecture/core/automation.html) to implement tag-based behaviours.

For example, the tag `cm-delete` can be used to mark a resource for [scheduled deletion](/cloudmarque/reference/tags/common/cm-delete.html). However, the automated process which searches for resources with this tag and deletes the marked resource must be provisioned and appropriatedly scheduled.