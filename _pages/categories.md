---
layout: page
permalink: /commonplace/
title: Commonplace
---

Cultivation - the art of cultivating mindfulness, wisdom, and stillness, while clearing out mental delusions and clinging. May include sharing of life principles, long-term goals.

Connection - the art of reading, speaking, and listening. May include subsuming of blogs, books, and other media.

Creativity - the art of making, writing, and playing. May include projects such as this website.

Constitution - the art of living well. May include physical health discussions, living spaces, cooking.

Currency - the art of caring for one's requisites in sustaining life. May include budgeting, financial independence discussions.



<div id="archives">
{% for category in site.categories %}
  <div class="archive-group">
    {% capture category_name %}{{ category | first }}{% endcapture %}
    <div id="#{{ category_name | slugize }}"></div>
    <p></p>
    
    <h3 class="category-head">{{ category_name }}</h3>
    <a name="{{ category_name | slugize }}"></a>
    {% for post in site.categories[category_name] %}
    <article class="archive-item">

          {% for tag in post.tags %}
          {% capture tag_name %}{{ tag }}{% endcapture %}
          <a href="/tag/{{ tag_name }}"><nobr>{{ tag_name }}</nobr></a>
          {% endfor %}
    ·   
      <a href="{{ site.baseurl }}{{ post.url }}">{% if post.title and post.title != "" %}{{post.title}}{% else %}{{post.excerpt |strip_html}}{%endif%}</a>   


    </article>
    {% endfor %}

{% endfor %}

<!--
<h1>All Tags</h1>
{% capture temptags %}
  {% for tag in site.tags %}
    {{ tag[1].size | plus: 1000 }}#{{ tag[0] }}#{{ tag[1].size }}
  {% endfor %}
{% endcapture %}
{% assign sortedtemptags = temptags | split:' ' | sort | reverse %}
{% for temptag in sortedtemptags %}
  {% assign tagitems = temptag | split: '#' %}
  {% capture tagname %}{{ tagitems[1] }}{% endcapture %}
  <a href="/tag/{{ tagname }}"><nobr>{{ tagname }}</nobr></a>
{% endfor %}
-->
  </div>
</div>