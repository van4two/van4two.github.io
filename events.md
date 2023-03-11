---
layout: home
---

{% include map.html category="event" %}

<div class="tiles">
  {% for post in site.posts %}
    {% if post.categories contains "event" %}

      <a href="{{post.url}}" class="tile-link">
        <div class="tile">
          <img src="{{post.teaser | liquify}}" alt="" class="tile-img">
          <div class="tile-overlay">
            <div class="tile-title">{{post.title}}</div>
          </div>
        </div>
      </a>
      
    {% endif %}
  {% endfor %}
</div>
