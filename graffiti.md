---
layout: page
title: Graffiti
permalink: /graffiti/
---

I've been documenting graffiti for your viewing pleasure.

These were from the first run on a shitty camera on a decent Alcatel phone. Next run I'll have a decent camera ready. I'm planning on sitting around waiting for multiple trains soon.

## Album

{% for image in site.static_files %}
    {% if image.path contains 'images/graffiti' %}
![image]({{ site.baseurl }}{{ image.path }})
    {% endif %}
{% endfor %}
