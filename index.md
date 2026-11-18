---
permalink: /
subtitle: PhD in Robot Learning | University of Edinburgh | Honda Research Institute Europe
---
{% include person-jsonld.html %}
<header class="intro">
  <h1>{{ site.title }}</h1>
  <p class="subtitle">{{ page.subtitle }}</p>
</header>

<aside class="profile">
<img src="{{ '/assets/img/profile_pic.jpeg' | relative_url }}" alt="Andreas Sochopoulos" width="400" height="400" fetchpriority="high">
{% include socials.html %}
</aside>

I am currently a PhD student at the University of Edinburgh (UoE), supported by Honda Research Institute Europe (HRI-EU), and advised by [Sethu Vijayakumar](https://homepages.inf.ed.ac.uk/svijayak/) (UoE), [Michael Gienger](https://scholar.google.com/citations?user=oU2jyxMAAAAJ&hl=de) (HRI-EU).

My research focuses on foundation models in robotics that use continuous-time generative models, such as diffusion and flow models. So far, I have worked on accelerating the inference of flow models for action generation without additional training overhead and efficient RL post-training . I am particularly interested in generalist policy post-training with as little intervention as possible.

I am currently exploring demonstration-efficient VLA steering from human videos and VLM suggestions. If you are interested in my research or would like to discuss related topics, feel free to reach out!

<h2><a href="{{ '/news/' | relative_url }}">News</a></h2>
{% include news.html limit=5 %}

<h2><a href="{{ '/publications/' | relative_url }}">Selected Publications</a></h2>
<div class="pubs">
{%- for p in site.data.publications %}{% if p.selected %}
{% include publication.html pub=p %}
{%- endif %}{% endfor %}
</div>
