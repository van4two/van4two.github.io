---
layout: cover
categories: [cover, europa]
title: Fuerteventura
#tags: [area geotermale, cascate, geyser, fotografia, spiaggia, bird watching, ghiacciaio, scogliere, fiordi]
#gallery_url: https://photos.app.goo.gl/P7VpaVGc6CMoSQYV8
path: fuerteventura

image: /assets/img/2017-12-16-fuerteventura/cover.jpg

carousels:
  - images: 
    - image: /assets/img/2017-12-16-fuerteventura/slider/01.jpg
    - image: /assets/img/2017-12-16-fuerteventura/slider/02.jpg
    - image: /assets/img/2017-12-16-fuerteventura/slider/03.jpg
    - image: /assets/img/2017-12-16-fuerteventura/slider/04.jpg
    - image: /assets/img/2017-12-16-fuerteventura/slider/05.jpg
    - image: /assets/img/2017-12-16-fuerteventura/slider/06.jpg
    - image: /assets/img/2017-12-16-fuerteventura/slider/07.jpg
    - image: /assets/img/2017-12-16-fuerteventura/slider/08.jpg
    - image: /assets/img/2017-12-16-fuerteventura/slider/09.jpg
    - image: /assets/img/2017-12-16-fuerteventura/slider/10.jpg
  
diary: fuerteventura
entries_layout: grid

location:
  longitude: -14.0537
  latitude: 28.3587
  ok: true

# {% contentfor sidebar %}

# | ----------- |
# | **Durata**      |
# | 20 gg (29 Giugno - 18 Luglio 2019)   |
# | **Distanza percorsa** |
# | 5650 km |
# | **Costo pp**      |
# | 1250 eur  |
# | **Mezzo di trasporto** |
# | Campervan (FIAT Scudo 2003) |

# {% endcontentfor %}
---

{% contentfor mymap %}
<iframe src="https://www.google.com/maps/d/embed?mid=1u7fufK2RqOmEy8EG3OqdKvnB9o3EQdVr&ehbc=2E312F" width="640" height="480"></iframe>
{% endcontentfor %}

{% include carousel.html height="50" unit="%" duration="7" number="1" %}

COMING SOON

<div class="entries-{{ page.entries_layout }}">
  {% for post in site.posts reversed %}
    {% if post.cat contains page.diary %}
      {% include diary-single.md type=page.entries_layout %}
    {% endif %}
  {% endfor %}
</div>
