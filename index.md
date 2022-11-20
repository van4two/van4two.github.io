---
layout: home
---

<!-- Google Map-->
{% include map.html category="cover" %}

<div class="tiles">
  {% for post in site.posts %}
    {% if post.layout contains "cover" and post.location.ok %}
    <div class="tile">
      <a href="{{ post.url }}" class="">
        <img src="{{ post.image }}" alt="" class="tile-img">
        <div class="tile-overlay">{{post.title}}</div>
      </a>
    </div>
    {% endif %}
  {% endfor %}
</div>
