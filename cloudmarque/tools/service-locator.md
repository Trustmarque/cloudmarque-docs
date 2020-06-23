---
title: Service Locator
summary: Cloudmarque leverages a Service Locator pattern to reliably allow different cloud resources to identify their dependencies.
---
Cloud resources often have dependencies on other cloud resources, some of which are necessary for operation of the resource, or are needed to enable certain resource features or behaviours.

For example, almost every cloud resource in Azure can be connected to Log Analytics which serves as a centralised logging capability. As each resource is deployed it needs to locate this capability (potentially among several possibilities) and link itself to provide logging capabilities.

While each resource has a name, there are several reasons why the resource name isn't flexible enough to serve as the primary identifier of a service in a cloud environment:

 * Restrictions on resource names make it difficult to reliably predict a resource name based on its purpose.
 * Immutable infrastructure patterns result in environments where high numbers of resources are created and destroyed, making it hard to identify the current "correct" resource providing a particular role in an environment.
 * Few resources can be renamed after they have been created, making it impossible to change the resource providing a service without redeploying it.

Cloudmarque introduces a standard tag to provide a canonical name for a service: **[cm-service](/cloudmarque/reference/tags/common/cm-service.html)**.

The value of this tag can be any string value. It can be leveraged to support any naming convention required for your cloud environment including logical roles, versioning, and partitioning.

## Standard dependencies
Each Cloudmarque component uses a standard configuration to list the services provided and dependencies:

{% highlight yaml linenos %}
# A list of services provided by the component
services:
  compute: "core.iaas.apps.hr"
# A list of dependencies needed by the component
dependencies:
  logging: "core.logging"
{% endhighlight %}

In this example, the component is publishing a new compute service identified by the moniker "core.iaas.apps.hr". Subsequent services which rely on this compute workload may include this identifier in their "dependencies" list.

This example also notes a dependency on a logging component. Here, Cloudmarque will search for a logging component with the `cm-service` tag of `core.logging` (the default for the core Log Analytics instance in Azure). Documentation for each component explains its dependencies.

The service locator operates at the subscription scope: it searches for components with the target `cm-service` tag value in the subscription set in current context.

## Versioning
As the `cm-service` tag can be any string, it can be co-opted to enable versioning. A tag value of `core.logging.2` could be used to identify an improved logging service such that cloud resources can have their dependency changed to the new version over time. This supports patterns such as [blue-green cloud infrastructure deployments](https://martinfowler.com/bliki/BlueGreenDeployment.html).

## Partitioning
Similarly, the `cm-service` tag can be used to enable partitioning. A tag values of `finance.logging` and `business.logging` could be used to identify separate logging services managed by different cloud teams ("Finance" and "Business") where operational support teams are required to separate access to system logs for different parts of an organisation.