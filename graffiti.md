---
layout: page
title: Graffiti
permalink: /graffiti/
---

I've been documenting graffiti for your viewing pleasure.

## Album

<div class='container'>
{% for image in site.static_files %}
    {% if image.path contains 'images/graffiti' %}
<div class="image">
    <a target="_blank" href="{{ site.baseurl }}{{ image.path }}">
        <img src="{{ site.baseurl }}{{ image.path }}" width="250" height="175">
    </a>
</div>
    {% endif %}
{% endfor %}
</div>