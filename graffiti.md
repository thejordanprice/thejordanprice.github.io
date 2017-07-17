---
layout: page
title: Graffiti
permalink: /graffiti/
---

I've been documenting graffiti for your viewing pleasure.

## Album
<script src="/js/lightbox.js">
<div class='container'>
{% for image in site.static_files %}
    {% if image.path contains 'images/graffiti' %}
<a target="_blank" href="{{ site.baseurl }}{{ image.path }}">
    <img src="{{ site.baseurl }}{{ image.path }}" onclick="lightbox(this)">
</a>
    {% endif %}
{% endfor %}
</div>