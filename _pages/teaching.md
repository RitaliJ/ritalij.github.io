---
layout: page
permalink: /teaching/
title: teaching
description: Courses I have TAed at Caltech.
nav: true
nav_order: 4
---

{% assign teaching_entries = site.teachings | sort: "importance" %}
{% for entry in teaching_entries %}
<div class="card mt-3">
  <div class="card-body">
    <h5 class="card-title">{{ entry.title }}</h5>
    <p class="card-text">{{ entry.description }}</p>
    {{ entry.content }}
  </div>
</div>
{% endfor %}
