---
layout: default
title: 一个简单的Github博客网页
---

<div>
  <h1>{{ page.title }}</h1>
  <ul>
    {% for post in site.posts %}
      <li><span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{site.baseurl}}{{post.url}}">{{ post.title }}</a></li>
    {% endfor %}
  </ul>
</div>
