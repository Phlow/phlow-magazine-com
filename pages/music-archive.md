---
nav_title           : MP3
title               : MP3 Music Archive
permalink           : /free-mp3-music-download/
---
<h2>Categories</h2>
<ul>
{% assign categories_list = site.categories %}
{% if categories_list.first[0] == null %}

    {% for category in categories_list %}
      {% if
        category[0] == 'Charts' or
        category[0] == 'News' or
        category[0] == 'Music Video' or
        category[0] == 'DJ/Liveact Mix' or
        category[0] == 'Music Marketing Promotion' or
        category[0] == 'Interview Portrait' or
        category[0] == 'Feature'
      %}
      {% else %}
        <li><a href="#{{ category | downcase | downcase | url_escape | strip | replace: ' ', '-' }}">{{ category | camelcase }}</a> // {{ site.tags[category].size }}</li>
      {% endif %}
    {% endfor %}

{% else %}
  {% for category in categories_list %}
    {% if
      category[0] == 'Charts' or
      category[0] == 'News' or
      category[0] == 'Music Video' or
      category[0] == 'DJ/Liveact Mix' or
      category[0] == 'Music Marketing Promotion' or
      category[0] == 'Interview Portrait' or
      category[0] == 'Feature'
    %}
    {% else %}
        <li><a href="#{{ category[0] | downcase | url_escape | strip | replace: ' ', '-' }}">{{ category[0] | camelcase }}</a></li>
    {% endif %}
  {% endfor %}


{% endif %}
{% assign categories_list = nil %}
</ul>

{% for category in site.categories %}
{% if
  category[0] == 'Charts' or
  category[0] == 'News' or
  category[0] == 'Music Video' or
  category[0] == 'DJ/Liveact Mix' or
  category[0] == 'Music Marketing Promotion' or
  category[0] == 'Interview Portrait' or
  category[0] == 'Feature'
%}
{% else %}

  <ul class="side-nav">
  <li class="heading" id="{{ category[0] | downcase | url_escape | strip | replace: ' ', '-' }}">{{ category[0] | camelcase }} // {{ category[1].size }} reviews</li>
  <li class="divider"></li>
    {% assign pages_list = category[1] %}
    {% for post in pages_list %}
      {% if post.title != null %}
      {% if group == null or group == post.group %}
      <li><a href="{{ site.url }}{{ post.url }}">{{ post.title }} <time datetime="{{ post.date | date_to_xmlschema }}" itemprop="datePublished">{{ post.date | date: "%B %d, %Y" }}</time></a></li>
      {% endif %}
      {% endif %}
    {% endfor %}
    {% assign pages_list = nil %}
    {% assign group = nil %}
  </ul>


{% endif %}
{% endfor %}