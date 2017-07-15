---
layout: page
title: Graffiti
permalink: /graffiti/
---

I've been documenting graffiti for your viewing pleasure.

These were from the first run on a shitty camera on a decent Alcatel phone. Next run I'll have a decent camera ready. I'm planning on sitting around waiting for multiple trains soon. I'll also be smart and generate thumbnails so each one isn't loading that giant picture for the little spot. Probably some type of image viewer coming too.

## Album

{% for image in site.static_files %}
    {% if image.path contains 'images/graffiti' %}
{::nomarkdown}
<div class="gallery">
  <a target="_blank" href="{{ site.baseurl }}{{ image.path }}">
    <img src="{{ site.baseurl }}{{ image.path }}" width="300" height="200">
  </a>
</div>
{:/}
    {% endif %}
{% endfor %}
