---
layout: page
title: Graffiti
permalink: /graffiti/
---

I've been documenting graffiti for your viewing pleasure.

## Album

<script src="/js/lightbox.js">

{% for image in site.static_files %}
    {% if image.path contains 'images/post/2017-7-16' %}
{::nomarkdown}
<img src="{{ site.baseurl }}{{ image.path }}" onclick="lightbox(this)">
{:/}
    {% endif %}
{% endfor %}