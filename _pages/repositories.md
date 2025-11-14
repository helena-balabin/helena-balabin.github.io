---
layout: page
permalink: /code/
title: code
description: While I am far from a perfect coder, I am commited to writing clean, reproducible, open-source code. This is a non-exhaustive list of some of the repositories I have worked on in the past years.
nav: true
nav_order: 4
---

{% if site.data.repositories.github_repos %}

<div class="repositories d-flex flex-wrap flex-md-row flex-column justify-content-between align-items-center">
  {% for repo in site.data.repositories.github_repos %}
    {% include repository/repo.liquid repository=repo %}
  {% endfor %}
</div>
{% endif %}
