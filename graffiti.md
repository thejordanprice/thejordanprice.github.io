---
layout: page
title: Graffiti
permalink: /graffiti/
---

I've been documenting graffiti for your viewing pleasure.

## Album

{% for image in site.static_files %}
    {% if image.path contains 'images/graffiti' %}
        ![image]({{ site.baseurl }}{{ image.path }})
    {% endif %}
{% endfor %}
