---
layout: home
feature_row:
  - image_path: /assets/images/unsplash-gallery-image-1-th.jpg
    alt: "placeholder image 1"
    title: "Placeholder 1"
    excerpt: "This is some sample content that goes here with **Markdown** formatting."
  - image_path: /assets/images/unsplash-gallery-image-2-th.jpg
    alt: "placeholder image 2"
    title: "Placeholder 2"
    excerpt: "This is some sample content that goes here with **Markdown** formatting."
    url: "#test-link"
    btn_label: "Read More"
    btn_class: "btn--inverse"
  - image_path: /assets/images/unsplash-gallery-image-3-th.jpg
    title: "Placeholder 3"
    excerpt: "This is some sample content that goes here with **Markdown** formatting."
---

<!-- Google Map-->
{% include map.html %}

<div class="tiles">
  {% for post in site.posts %}
    {% if post.layout contains "cover" %}
    <div class="tile">
      <img src="{{ post.image }}" alt="" class="tile-img">
      <a href="{{ post.url }}" class="tile-overlay"> {{ post.title }} </a>
    </div>
    {% endif %}
  {% endfor %}
</div>