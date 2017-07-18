---
layout: page
title: Graffiti
permalink: /graffiti/
comments: true
---

I've been documenting graffiti for your viewing pleasure.

## Album

{::nomarkdown}
<div class='container' style='text-align: center;'>
{:/}

{% for image in site.static_files %}
    {% if image.path contains 'images/graffiti' %}
{::nomarkdown}
<img class='lightbox' src="{{ site.baseurl }}{{ image.path }}" onclick="lightbox(this)">
{:/}
    {% endif %}
{% endfor %}

{::nomarkdown}
</div>
{:/}

{::nomarkdown}
<script src="/js/lightbox.js"></script>
<script>
var images = document.getElementsByClassName('lightbox');
var loaded = false;
for (let image in images) {
    if (images[image]) {
        var metadata = [];
        image = images[image];
        metadata.src = image.src;
        metadata.strings = metadata.src.split('/');
        metadata.folder = metadata.strings[4].toString();
        metadata.filename = metadata.strings.pop() || metadata.strings.pop();
        metadata.parts = metadata.filename.split('.');
        metadata.name = metadata.parts[0].toString();
        metadata.ext = metadata.parts[1].toString();
        metadata.thumb = metadata.name + "_tn." + metadata.ext;
        image.src = "/images/thumbnails/" + metadata.folder + "/" + metadata.thumb;
        window.addEventListener("load", function(){
            loaded = true;
        });
        if (loaded = true) {
            image.src = metadata.src;
        };
    };
};
</script>
{:/}

{% include disqus.html %}