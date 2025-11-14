---
layout: page
permalink: /values/
title: values
nav: true
nav_order: 9
---

<!-- markdownlint-disable MD033 -->

{% assign values = site.data.values | default: site.empty_array %}
{% if values and values != empty %}

<p class="mb-3" style="font-size: 1.1rem;">I know, I know, I am very aware that I am still early in my career, why would anyone care about my takes on academia? (And of course, I am not forcing anyone to read this.) However, I have realized that showing what I care about through how I approach work is far healthier for me than giving up. This non-exhaustive list serves both as a personal reflection and and a way to encourage open discussion while staying accountable.</p>
<ul class="values-list" style="font-size: 1.05rem;">
  {% for item in values %}
    {% assign first_sentence = item %}
    {% assign remainder = '' %}
    {% if item contains '. ' %}
      {% assign first_sentence = item | split: '. ' | first %}
      {% assign remainder = item | remove_first: first_sentence %}
      {% assign remainder = remainder | remove_first: '. ' %}
    {% endif %}
  <li class="mb-2"><strong>{{ first_sentence }}{% if item contains '. ' %}.{% endif %}</strong>{% if remainder != '' %} {{ remainder }}{% endif %}</li>
  {% endfor %}
</ul>
{% else %}
<p>No values listed yet. Update <code>_data/values.yml</code> to populate this page.</p>
{% endif %}
<!-- markdownlint-enable MD033 -->
