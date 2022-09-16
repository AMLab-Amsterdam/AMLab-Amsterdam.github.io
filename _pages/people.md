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
{%- for category in page.display_categories -%}

<h2 class="category">{{ category }}</h2>

{%- assign categorized_people = site.people | where: "category", category -%}
{%- assign ordered_people = categorized_people | group_by: "order" -%}
{%- assign ordered_people = ordered_people | sort: "name" -%}

<div class="grid">
{%- for o in ordered_people -%}
{%- assign sorted_people = o.items | sort_natural: "last_name" -%}  
<!-- Generate cards for each person -->
  {%- for person in sorted_people -%}
    {% include person_card.html %}
  {%- endfor %}
{%- endfor -%}
</div>
{%- endfor -%}
</div>
