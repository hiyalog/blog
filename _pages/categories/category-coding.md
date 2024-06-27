---
title: "Coding Record"
layout: archive
permalink: categories/coding
author_profile: true
sidebar_category: true
---

{% assign posts = site.categories['coding'] %}
{% for post in posts %} {% include archive-single2.html type=page.entries_layout %} {% endfor %}
