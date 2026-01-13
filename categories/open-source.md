---
layout: page
title: "开源项目"
permalink: /categories/open-source/
---

# 开源项目

## 项目计划
1. **MiniGameServer** - 轻量级C++游戏服务器框架
2. **其他实践项目** - 将所学应用于实际开发

## 学习目标
- 实践现代C++编程
- 学习项目架构设计
- 掌握Git协作流程
- 参与开源社区

## 相关文章
{% for post in site.categories.open-source %}
- [{{ post.title }}]({{ post.url }}) - {{ post.date | date: "%Y-%m-%d" }}
{% endfor %}

---

[查看所有分类](/categories/) | [返回首页](/)
