---
title: "Bài đăng mới nhất"
keywords: sample homepage
tags: [latest_articles]
sidebar: mydoc_sidebar
toc: false
permalink: index.html
---

<div class="post-list">
    {% for post in site.posts limit:10 %}


<h2><a class="post-link" href="{{ post.url | remove: "/" }}">{{ post.title }}</a></h2>
    <span class="post-meta">{{ post.date | date: "%b %-d, %Y" }} /
        {% for tag in post.tags %}

            <a href="{{ "tag_" | append: tag | append: ".html"}}">{{tag}}</a>{% unless forloop.last %}, {% endunless%}

            {% endfor %}</span>
    <p>{% if page.summary %} {{ page.summary | strip_html | strip_newlines | truncate: 160 }} {% else %} {{ post.content | truncatewords: 50 | strip_html }} {% endif %}</p>

    {% endfor %}

    <p><a href="feed.xml" class="btn btn-primary navbar-btn cursorNorm" role="button">RSS Subscribe{{tag}}</a></p>

<hr />
</div>

## Xem thêm bài viết

{% include links.html %}
