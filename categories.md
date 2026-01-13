---
layout: page
title: "所有分类"
permalink: /categories/
---

# 📚 所有分类

{% for category in site.categories %}
## {{ category[0] }}
{% for post in category[1] %}
- [{{ post.title }}]({{ post.url }}) - {{ post.date | date: "%Y-%m-%d" }}
{% endfor %}
{% endfor %}

---

[返回首页](/)
