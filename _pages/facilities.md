---
layout: page
title: facilities
permalink: /facilities/
icon-fa: fa-solid fa-microscope
description: We utilize the state-of-the-art EM facility in AADC KIST, advancing TEM research and application in materials science.
nav: true
nav_order: 4
display_categories: [TEM, Holder, FIB, SEM, Others]
horizontal: true
type: facility
---

NOTE: This page is under construction. <i class="fa-solid fa-person-digging"></i>

<!-- pages/facilities.md -->
<div class="facilities">
{% if site.enable_facility_categories and page.display_categories %}
  <!-- Display categorized facilities -->
  {% for category in page.display_categories %}
  <a id="{{ category }}" href=".#{{ category }}">
    <h2 class="category">{{ category }}</h2>
  </a>
  {% assign categorized_facilities = site.facilities | where: "category", category %}
  {% assign sorted_facilities = categorized_facilities | sort: "importance" %}
  <!-- Generate cards for each facility -->
  {% if page.horizontal %}
  <div class="container">
    <div class="row row-cols-2">
    {% for facility in sorted_facilities %}
      {% include facilities_horizontal.liquid %}
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="grid">
    {% for facility in sorted_facilities %}
      {% include facilities.liquid %}
    {% endfor %}
  </div>
  {% endif %}
  {% endfor %}

{% else %}

<!-- Display facilities without categories -->

{% assign sorted_facilities = site.facilities | sort: "importance" %}

  <!-- Generate cards for each project -->

{% if page.horizontal %}

  <div class="container">
    <div class="row row-cols-2">
    {% for project in sorted_facilities %}
      {% include facilities_horizontal.liquid %}
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="grid">
    {% for project in sorted_facilities %}
      {% include facilities.liquid %}
    {% endfor %}
  </div>
  {% endif %}
{% endif %}
</div>
