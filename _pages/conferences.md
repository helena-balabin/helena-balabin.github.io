---
layout: page
permalink: /conferences/
title: conferences
description: I am lucky I get to travel for work and I do not take it for granted. Here are some of my favorite moments from the conferences I have attended over the past few years.
nav: true
nav_order: 8
---

<!-- markdownlint-disable MD033 -->
<style>
  .conferences-gallery {
    text-align: center;
  }

  .conferences-gallery .conference-group {
    text-align: center;
  }

  .conferences-gallery .conference-group .row {
    justify-content: center;
  }

  .conferences-gallery .conference-group .figure-caption {
    font-size: 0.95rem;
  }

  @media (min-width: 768px) {
    .conferences-gallery .conference-photo {
      flex: 0 0 50%;
      max-width: 50%;
    }
  }
</style>

{% assign conferences = site.data.conferences | sort: 'start_date' | reverse %}
{% if conferences and conferences != empty %}

<div class="conferences-gallery">
  {% for conference in conferences %}
    <section class="conference-group mb-5">
      <h2 class="h3 mb-1">{{ conference.name }}</h2>
      {% if conference.location or conference.dates %}
        <p class="text-muted">{{ conference.location }}{% if conference.location and conference.dates %} · {% endif %}{{ conference.dates }}</p>
      {% endif %}
      {% if conference.gallery and conference.gallery != empty %}
        <div class="row">
          {% for item in conference.gallery %}
            <div class="col-lg-4 col-md-6 col-sm-8 col-10 mb-4 conference-photo">
              <figure class="figure w-100 mx-auto">
                <img src="{{ item.image | relative_url }}" class="figure-img img-fluid rounded" alt="{{ item.alt | default: item.caption }}" loading="lazy">
                {% if item.caption %}
                  <figcaption class="figure-caption">{{ item.caption }}</figcaption>
                {% endif %}
              </figure>
            </div>
          {% endfor %}
        </div>
      {% else %}
        <p class="mb-0">Gallery coming soon.</p>
      {% endif %}
    </section>
  {% endfor %}
</div>
{% else %}
<p>No conferences added yet. Update <code>_data/conferences.yml</code> with your photos and details.</p>
{% endif %}
<!-- markdownlint-enable MD033 -->
