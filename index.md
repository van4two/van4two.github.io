---
layout: home
---

<!-- Google Map-->
{% include map.html category="cover" %}

<div class="tiles">
  {% for post in site.posts %}
    {% if post.layout contains "cover" and post.location.ok %}

      <a href="{{post.url}}" class="tile-link">
        <div class="tile">
          <img src="{{post.image}}" alt="" class="tile-img">
          <div class="tile-overlay">
            <div class="tile-title">{{post.title}}</div>
          </div>
        </div>
      </a>

    {% endif %}
  {% endfor %}
</div>
