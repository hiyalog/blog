---
title: "Daily 기록"
layout: archive
permalink: categories/daily
author_profile: true
sidebar_category: true
---


{% assign posts = site.categories.daily %}
{% for post in posts %} {% include archive-single.html type=page.entries_layout %} {% endfor %}
