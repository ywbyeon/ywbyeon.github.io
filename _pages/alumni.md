---
layout: page
title: alumni
permalink: /alumni-AEML/
description: Alumni of the Advanced Electron Microscopy Lab (AEML)
icon-fa: fa-solid fa-graduation-cap
nav: false
nav_order: 8
display_categories: [undergrad] #postdoc, intern, graduate student, alumni (해당되는 것 추가)
horizontal: false
---

<!-- pages/alumni.md -->
<div class="members">
{% if page.display_categories %}
  <!-- Display categorized members -->
  {% for category in page.display_categories %}
  <a id="{{ category }}" href=".#{{ category }}">
    <h2 class="category">{{ category }}</h2>
  </a>
  {% assign categorized_members = site.members | where: "category", category | where: "status", "alumni" %}
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

{% assign sorted_members = site.members | where: "status", "alumni" | sort: "importance" %}

  <!-- Generate items for each member -->
  <div class="row row-cols-1 row-cols-md-3">
    {% for member in sorted_members %}
      {% include members.liquid %}
    {% endfor %}
  </div>
{% endif %}
</div>


<!--
## 졸업생

### 박사 졸업생

| 이름 | 신분 | 기간 | 역할 | 현재 정보 |
|------|------|------|------|-----------|
| 김창인 | 박사과정 | 2018.03 - 2023.02 | 연구원 | 삼성전자 |
| 김대현 | 박사과정 | 2018.03 - 2023.02 | 연구원 | 삼성전자 |
| 김해나 | 박사과정 | 2018.03 - 2023.02 | 연구원 | 삼성전자 |
| 김희원 | 박사과정 | 2018.03 - 2023.02 | 연구원 | 삼성전자 |
| 곽성훈 | 박사과정 | 2018.03 - 2023.02 | 연구원 | 삼성전자 |

### 석사 졸업생

| 이름 | 신분 | 기간 | 역할 | 현재 정보 |
|------|------|------|------|-----------|
| 홍길동 | 석사과정 | 2020.03 - 2022.02 | 연구원 | 삼성전자 |
| 김철수 | 석사과정 | 2020.03 - 2022.02 | 연구원 | 삼성전자 | 
-->