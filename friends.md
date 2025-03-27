---
layout: default
title: Friends
---

# 👥 Friends Page  

## Teman-Teman Saya di Kelas  :

<ol>
{% for friend in site.data.friends %}
<li>
    <a href="{{ friend.link }}" target="_blank">{{ friend.name }}</a>
</li>
{% endfor %}
</ol>
