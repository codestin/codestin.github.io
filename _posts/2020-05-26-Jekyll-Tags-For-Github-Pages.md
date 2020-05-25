---
layout: post
title: Jekyll Tags for Github Pages
author: christin
categories: [Creativity]
tags: Webdev
---

I was stuck on figuring out how to generate tags for posts using Jekyll hosted by Github Pages for a while. Github Pages is great because it is free and integrated into the git version control provided by Github, but they do not allow most Ruby Gems like...jekyll-tags! After a lot of hunting on the internet, I would like to sing some praises for these [instructions](https://longqian.me/2017/02/09/github-jekyll-tag/) by Long Qian, because they were the only ones that worked for me in a straightforward manner. 

I also want to share one tidbit I figured out after some fiddling with Jekyll's Liquid template language. For example, on the [Commonplace](https://christinchong.com/commonplace/) page, I wanted to be able to display the entry's tag next to the entry's name. Here's the code that works for me.

{% raw %}
```liquid
{% assign rawtags = "" %}
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
```
{% endraw %}

In addition, on a meta-level, I could not figure out how to share my code above without Jekyll trying to render it and breaking in the process. I was able to solve this by going into Long Qian's [raw Markdown post](https://github.com/qian256/qian256.github.io/blob/master/_posts/2017-02-09-github-jekyll-tag.md) on github.

Next to fix is the pygments highlighting theme...not a huge fan of the big block of dark mode above! My goal is to understand all aspects of this Jekyll theme and open source it after some clean up.