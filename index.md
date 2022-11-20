---
layout: home
---

<!-- Google Map-->
{% include map.html %}

<div class="tiles">
  {% for post in site.posts %}
    {% if post.layout contains "cover" and post.location.ok %}
    <div class="tile">
      <img src="{{ post.image }}" alt="" class="tile-img">
      <a href="{{ post.url }}" class="tile-overlay"> {{ post.title }} </a>
    </div>
    {% endif %}
  {% endfor %}
</div>