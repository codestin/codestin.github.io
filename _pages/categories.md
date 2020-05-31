---
layout: page
permalink: /commonplace/
title: Commonplace
---

<div id="archives">
<h2 class="category-head">Cultivation</h2>
The art of cultivating mindfulness, wisdom, and stillness, while reducing clinging. May include sharing of life principles, long-term goals. 
{% for post in site.categories.Cultivation %}
   <article class="archive-item">

          {% for tag in post.tags %}
          {% capture tag_name %}{{ tag }}{% endcapture %}
          <a href="/tag/{{ tag_name }}"><nobr>{{ tag_name }}</nobr></a>
          {% endfor %}
    >> 
      <a href="{{ site.baseurl }}{{ post.url }}">{% if post.title and post.title != "" %}{{post.title}}{% else %}{{post.excerpt |strip_html}}{%endif%}</a>   
  </article>
{% endfor %}
<hr>
<h2 class="category-head">Connection</h2>
The art of reading, speaking, and listening. May include subsuming of blogs, books, and other media.
{% for post in site.categories.Connection %}
   <article class="archive-item">

          {% for tag in post.tags %}
          {% capture tag_name %}{{ tag }}{% endcapture %}
          <a href="/tag/{{ tag_name }}"><nobr>{{ tag_name }}</nobr></a>
          {% endfor %}
    >> 
      <a href="{{ site.baseurl }}{{ post.url }}">{% if post.title and post.title != "" %}{{post.title}}{% else %}{{post.excerpt |strip_html}}{%endif%}</a>   
  </article>
{% endfor %}
<hr>
<h2 class="category-head">Creativity</h2>
The art of making, writing, and playing. May include projects such as this website. 
{% for post in site.categories.Creativity %}
   <article class="archive-item">

          {% for tag in post.tags %}
          {% capture tag_name %}{{ tag }}{% endcapture %}
          <a href="/tag/{{ tag_name }}"><nobr>{{ tag_name }}</nobr></a>
          {% endfor %}
    >> 
      <a href="{{ site.baseurl }}{{ post.url }}">{% if post.title and post.title != "" %}{{post.title}}{% else %}{{post.excerpt |strip_html}}{%endif%}</a>   
  </article>
{% endfor %}
<hr>
<h2 class="category-head">Constitution</h2>
The art of living well. May include physical health discussions, living spaces, cooking.
{% for post in site.categories.Constitution %}
   <article class="archive-item">

          {% for tag in post.tags %}
          {% capture tag_name %}{{ tag }}{% endcapture %}
          <a href="/tag/{{ tag_name }}"><nobr>{{ tag_name }}</nobr></a>
          {% endfor %}
    >> 
      <a href="{{ site.baseurl }}{{ post.url }}">{% if post.title and post.title != "" %}{{post.title}}{% else %}{{post.excerpt |strip_html}}{%endif%}</a>   
  </article>
{% endfor %}
<hr>
<h2 class="category-head">Currency</h2>
The art of caring for one's requisites in sustaining life. May include budgeting, financial independence discussions.
{% for post in site.categories.Currency %}
   <article class="archive-item">

          {% for tag in post.tags %}
          {% capture tag_name %}{{ tag }}{% endcapture %}
          <a href="/tag/{{ tag_name }}"><nobr>{{ tag_name }}</nobr></a>
          {% endfor %}
    >>
      <a href="{{ site.baseurl }}{{ post.url }}">{% if post.title and post.title != "" %}{{post.title}}{% else %}{{post.excerpt |strip_html}}{%endif%}</a>   
  </article>
{% endfor %}

<!--
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

  </div>
  -->
</div>