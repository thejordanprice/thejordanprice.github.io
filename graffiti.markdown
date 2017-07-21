---
layout: page
title: Graffiti
permalink: /graffiti/
description: "I've been documenting graffiti for your viewing pleasure."
---

## The Album
{::nomarkdown}
<div style='width: 100%; text-align: left;'>{% for image in site.static_files %}{% if image.path contains 'images/graffiti' %}<img class='img-responsive lightbox' src="{{ site.baseurl }}{{ image.path }}" onclick="lightbox(this)">{% endif %}{% endfor %}</div>
<script src="/js/lightbox.js"></script>
{:/}