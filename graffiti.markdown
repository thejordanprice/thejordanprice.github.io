---
layout: page
title: Graffiti
permalink: /graffiti/
description: "I've been documenting graffiti for your viewing pleasure."
---

### Graffiti
{::nomarkdown}
<div style='width:100%'>{% for image in site.static_files %}{% if image.path contains 'images/graffiti' %}<img class='lightbox' src="{{ site.baseurl }}{{ image.path }}" onclick="lightbox(this)">  {% endif %}{% endfor %}
</div>
<script src="/js/lightbox.js"></script>
{:/}