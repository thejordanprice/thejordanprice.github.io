---
layout: page
title: Graffiti
permalink: /graffiti/
---

I've been documenting graffiti for your viewing pleasure.

## Album

{% for image in site.static_files %}
    {% if image.path contains 'images/graffiti' %}
{::nomarkdown}
<img src="{{ site.baseurl }}{{ image.path }}" onclick="lightbox(this)">
{:/}
    {% endif %}
{% endfor %}

<script src="/js/lightbox.js">