---
layout: default
title: Lembar Pertama
---

# Lembar Pertama

Duduklah sebentar. Ada lembar baru.

## Serial

{% assign serials = site.lembar | group_by: "serial" %}
{% for s in serials %}
<section class="serial-card">
<h3>{{ s.name }}</h3>
<p class="serial-count">{{ s.items.size }} lembar</p>
<ul>
{% assign items = s.items | sort: "episode" %}
{% for ep in items %}
<li><a href="{{ ep.url | relative_url }}">Lembar {{ ep.episode }}: {{ ep.title }}</a></li>
{% endfor %}
</ul>
</section>
{% endfor %}
