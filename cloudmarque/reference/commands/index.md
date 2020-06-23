---
title: Commands
summary: An index of all the commands currently supported by Cloudmarque PowerShell Tools for Microsoft Azure.
tags: tags, automation, meta
---
This page is an auto-generated list of all PowerShell cmdlets in the `Cloudmarque.Azure` package.

{% if site.cm-commands.length > 0 %}
<ul>
    {% for cmd in site.cm-commands %}
    <li><a href="{{ cmd.url }}">{{ cmd.title }}</a></li>
    {% endfor %}
</ul>
{% else %}
<div class="alert alert-info" role="alert">
  <h4 class="alert-heading">Coming soon!</h4>
  <p>We are currently in the process of migrating our code to GitHub and reconfiguring build pipelines to automatically
  populate the command documentation.</p>
  <hr>
  <p class="mb-0">For more information, please see <a href="/blog/2020/06/12/docs/">this blog post</a>.</p>
</div>
{% endif %}