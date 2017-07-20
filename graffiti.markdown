---
layout: page
title: Graffiti
permalink: /graffiti/
header-img: "images/graffiti/IMG_20170713_133512.jpg"
description: "I've been documenting graffiti for your viewing pleasure."
---

## Album

{% for image in site.static_files %}
    {% if image.path contains 'images/graffiti' %}
{::nomarkdown}
<img class='lightbox' src="{{ site.baseurl }}{{ image.path }}" onclick="lightbox(this)">
{:/}
    {% endif %}
{% endfor %}

{::nomarkdown}
<script src="/js/lightbox.js"></script>
{:/}