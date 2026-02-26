---
layout: page
title: Contact
---

Email: **{{ site.data.profile.email }}**

You can also find me here:
{% for l in site.data.profile.links %}
- [{{ l.label }}]({{ l.url }})
{% endfor %}