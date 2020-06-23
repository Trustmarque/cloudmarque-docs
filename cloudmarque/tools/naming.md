---
title: Naming conventions
summary: Ensure your environment is easy to understand by adopting a clear naming convention for your cloud resources.
---
A standard naming convention helps IT staff understand the organisation of a cloud environment, streamlining triage, new service rollouts, and evaluation of change.

Cloudmarque provides a default naming convention that can be tailored to each organisation or cloud estate which is powered by a YAML configuration file in the root of a [Resources]() repository.

## Convention file
Naming conventions are defined by tokens and generators in a `naming.yaml` file:
{% highlight yaml linenos %}
tokens:
  organisation: tms
  salt: Acme Widgets
  estate: web        # Everything in the estate is "web"
  architecture:
    core: core 
    code: code
    iaas: iaas
    paas: paas
    endpoints: end
    security: sec
  environments:
    default: shr      # Shared
    development: dev
    integration: int
    test: tst
    production: prd
  resources:
    vm: vm
    network: net

generator:
 - name: default
   split: "-"
   case: lower
   fallback: random
   components: 
    - source: organisation
    - source: environment
    - source: resource
    - source: random
      max: 10
      min: 1
      digits: true
      characters: lower
 - name: random
   split: "-"
   case: lower
   fallback: random
   components:
    - source: random
{% endhighlight %}

## Generating a resource name
Call:

{% highlight powershell %}
Get-CmAzResourceName -Generator default -MaxLength 15 -Environment development -For VM
{% endhighlight %}

Results in: `tms-dev-vm-0d6t`

`Get-CmAzResourceName` is called internally by Cloudmarque tools, so the majority of the time you will not need to worry about generating resource names manually. However, for more information on how to use `Get-CmAzResourceName`, refer to the [Command Reference]().