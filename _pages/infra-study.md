---
layout: archive
title: "Infra Study"
permalink: /infra-study/
author_profile: true
---

欢迎来到我的 AI Infra 学习笔记。

{% assign grouped_notes = site.infra_study | group_by: "chapter" | sort: "name" %}

{% for chapter in grouped_notes %}
  <h3>{{ chapter.name }}</h3>
  <ul>
    {% assign sorted_items = chapter.items | sort: "order" %}
    {% for item in sorted_items %}
      <li>
        <a href="{{ item.url | relative_url }}">{{ item.title }}</a>
      </li>
    {% endfor %}
  </ul>
{% endfor %}
