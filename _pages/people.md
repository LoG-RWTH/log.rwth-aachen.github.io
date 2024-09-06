---
layout: page
title: People
permalink: /people/
description: Meet our group members
nav: true
nav_order: 2
display_categories: [Head, PhD Candidates, Student Assistant]
horizontal: false
---

<!-- pages/people.md -->
<div class="teams">
  <img src="/assets/img/team.jpg" alt="LoG Team" style="width:100%;height:100%;">
  {%- for category in page.display_categories %}
  <h2 class="category">{{ category }}</h2>
  {%- assign categorized_people = site.people | where: "category", category -%}
  {%- assign sorted_people = categorized_people | sort: "importance" %}
  <!-- Generate cards for each member -->
  <div class="grid">
    {%- for people in sorted_people -%}
      {% include teams.html %}
    {%- endfor %}
  </div>
  {% endfor %}
</div>
