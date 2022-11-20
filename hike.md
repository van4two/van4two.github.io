---
layout: hikes
entries_layout: grid
---

<!--
 Copyright 2022 van42.com.
 SPDX-License-Identifier: CC-BY-NC-ND-4.0
-->

{% include map.html category="hike" %}

<div class="entries-{{ page.entries_layout }}">
  {% for post in site.posts reversed %}
    {% unless post.categories contains "hike" %}{% continue %}{% endunless %}
    {% include hike-single.md type=page.entries_layout %}
  {% endfor %}
</div>
