---
layout: default
title: Blog
permalink: /blog/
---
Mostly, things that come up in books I read. Counterpoints are always appreciated & stated opinions are subject to change.

{% for post in site.posts %}
  {% unless post.tags contains 'private' %}
  <div id="post-short">
    <a href="{{site.url}}{{site.baseurl}}{{post.url}}">
      <h3>{{post.title}}</h3>
    </a>
    <i>posted on {{ post.date | date: "%-d %b %Y" }}</i>
    <p>
      {% if post.excerpt %}
        {{ post.excerpt }}
      {% else %}
        {{ post.content }}
      {% endif %}
    </p>
  </div>
  {% endunless %}
{% endfor %}
