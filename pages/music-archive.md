---
nav_title           : MP3
title               : MP3 Music Archive
permalink           : /free-mp3-music-download/
---
Choose your favorite music genre, visit a review and listen to the music!
{: .h4 }

<div class="grid col-3">
  <div>
    <h2>Dance</h2>
    <ul>
      <li><a href="{{ site.url }}{{ site.baseurl }}/music-genre/house">House</a></li>
      <li><a href="{{ site.url }}{{ site.baseurl }}/music-genre/techno">Techno</a></li>
      <li><a href="{{ site.url }}{{ site.baseurl }}/music-genre/hip-hop">Hip Hop</a></li>
      <li><a href="{{ site.url }}{{ site.baseurl }}/music-genre/dub-and-reggae">Dub and Reggae</a></li>
      <li><a href="{{ site.url }}{{ site.baseurl }}/music-genre/drum-and-bass">Drum and Bass</a></li>
    </ul>
  </div><!-- /col1 -->

  <div>
    <h2>Pop</h2>
    <ul>
      <li><a href="{{ site.url }}{{ site.baseurl }}/music-genre/pop">Pop</a></li>
      <li><a href="{{ site.url }}{{ site.baseurl }}/music-genre/downbeat">Downbeat</a></li>
      <li><a href="{{ site.url }}{{ site.baseurl }}/music-genre/rock">Rock</a></li>
      <li><a href="{{ site.url }}{{ site.baseurl }}/music-genre/folk-acoustic">Folk-Acoustic</a></li>
      <li><a href="{{ site.url }}{{ site.baseurl }}/music-genre/trip-hop">Trip Hop</a></li>
      <li><a href="{{ site.url }}{{ site.baseurl }}/music-genre/jazz">Jazz</a></li>
      <li><a href="{{ site.url }}{{ site.baseurl }}/music-genre/compilation">Compilation</a></li>
    </ul>
  </div><!-- /col2 -->

  <div>
    <h2>Electronic</h2>
    <ul>
      <li><a href="{{ site.url }}{{ site.baseurl }}/music-genre/idm">IDM</a></li>
      <li><a href="{{ site.url }}{{ site.baseurl }}/music-genre/electronica-indietronic">Electronica-Indietronic</a></li>
      <li><a href="{{ site.url }}{{ site.baseurl }}/music-genre/ambient">Ambient</a></li>
      <li><a href="{{ site.url }}{{ site.baseurl }}/music-genre/experimental">Experimental</a></li>
      <li><a href="{{ site.url }}{{ site.baseurl }}/music-genre/chip-music">Chip Music</a></li>
    </ul>
  </div><!-- /col3 -->
</div><!-- /grid -->



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
      <li><a href="{{ site.url }}{{ post.url }}">{{ post.title }}</a></li>
      {% endif %}
      {% endif %}
    {% endfor %}
    {% assign pages_list = nil %}
    {% assign group = nil %}
  </ul>


{% endif %}
{% endfor %}