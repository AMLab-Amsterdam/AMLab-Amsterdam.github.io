---
layout: page
title: People
permalink: /people/
description: 
nav: true
display_categories: [Staff, Postdocs, PhD Students]
---

<!-- pages/people.md -->
<div class="projects">
<!-- Display categorized people -->
{%- for category in page.display_categories %}
<h2 class="category">{{ category }}</h2>
{%- assign categorized_people = site.people | where: "category", category -%}
{%- assign sorted_people = categorized_people | sort: "order" %}
<!-- Generate cards for each person -->
<div class="grid">
  {%- for person in sorted_people -%}
    {% include person_card.html %}
  {%- endfor %}
</div>
{% endfor %}
</div>
