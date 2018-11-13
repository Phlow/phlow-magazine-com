---
nav_title           : Compilations
subtitle            : Free MP3 Music
title               : Creative Commons Music Compilations
permalink           : /creative-commons-compilation/
---
We try our best to collect only the best of the best. With this attitude we present you MP3-music published by netlabels which are freely available. All collections come around in a customer-friendly ZIP-Archive.
<!--more-->

Thank you for downloading!

## Exclusive compilations by Phlow-Magazine.com

Enjoy our free mp3 mixes with music licensed under a [creative commons](http://creativecommons.org).

<div class="grid col-4">
{% for post in site.posts %}
{% capture category %}{{ post.categories }}{% endcapture %}
{% if category contains 'ompilation' %}
<a class="card" href="{{ post.url | relative_url }}">
<div>
<img src="{{ site.url }}{{ site.baseurl }}/{{ post.image.title }}" alt="{{ post.title | escape }}">
</div>
</a>
{% endif %}
{% endfor %}
</div>
