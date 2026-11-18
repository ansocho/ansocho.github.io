---
title: Publications
permalink: /publications/
description: Publications by Andreas Sochopoulos on robot learning, imitation learning, and diffusion and flow-based policies.
---
{%- assign years = site.data.publications | group_by: "year" | sort: "name" | reverse %}
{%- for y in years %}
<h2 class="year">{{ y.name }}</h2>
<div class="pubs">
{%- for p in y.items %}
{% include publication.html pub=p %}
{%- endfor %}
</div>
{%- endfor %}
