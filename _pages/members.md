---
layout: page
permalink: /members-AEML/
title: members
description: Current members of the Advanced Electron Microscopy Lab (AEML)
icon-fa: fa-solid fa-users-viewfinder
nav: false
nav_order: 8
display_categories: [postdoc, intern] #graduate student, alumni, undergrad
horizontal: false
---

<!-- pages/members.md -->
<div class="members">
{% if page.display_categories %}
  <!-- Display categorized members -->
  {% for category in page.display_categories %}
  <a id="{{ category }}" href=".#{{ category }}">
    <h2 class="category">{{ category }}</h2>
  </a>
  {% assign categorized_members = site.members | where: "category", category | where: "status", "member" %}
  {% assign sorted_members = categorized_members | sort: "importance" %}
  <!-- Generate cards for each project -->
  <div class="row row-cols-1 row-cols-md-3">
    {% for member in sorted_members %}
      {% include members.liquid %}
    {% endfor %}
  </div>
  {% endfor %}

{% else %}
  <!-- Display members without categories -->

{% assign sorted_members = site.members | where: "status", "member" | sort: "importance" %}
  <!-- Generate items for each member -->
  <div class="row row-cols-1 row-cols-md-3">
    {% for member in sorted_members %}
      {% include members.liquid %}
    {% endfor %}
  </div>
{% endif %}
</div>
