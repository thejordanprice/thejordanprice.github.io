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
<!-- Trigger the Modal -->
<img id="albumImg" src="{{ site.baseurl }}{{ image.path }}" width="300" height="200">
<!-- The Modal -->
<div id="fullscreen" class="modal">
  <!-- The Close Button -->
  <span class="close" onclick="document.getElementById('fullscreen').style.display='none'">&times;</span>
  <!-- Modal Content (The Image) -->
  <img class="modal-content" id="{{ image.path }}">
</div>
{:/}
    {% endif %}
{% endfor %}
