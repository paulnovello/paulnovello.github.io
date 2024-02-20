---
layout: about
title: about
permalink: /
subtitle: <a href='#'>ML Research Engineer</a>, DEEL Team, IRT Saint Exupery, Toulouse.

profile:
  align: right
  image: prof_pic_paul.jpg 
  image_circular: false # crops the image to make it circular
  more_info: >
    <p>Myself 10 years ago.</p>
    <p>Still looking the same.<p>

news: true # includes a list of news items
latest_posts: false # includes a list of the newest posts
selected_papers: true # includes a list of papers marked as "selected={true}"
social: true # includes social icons at the bottom of the page
display_categories: [Roadmap]
horizontal: true
---

Hi, I am Paul, an ML Research Engineer interested in Safe/Trustworthy AI and Scientific ML, i.e. ML applied to scientific computing and physical simulations. While these two fields might appear poled apart, there are connections (believe me). If you're not convinced, see my research mindmap below.

I did my PhD at CESTA, Bordeaux's research center of the French Alternative Energies and Atomic Energy Commission (CEA); CMAP, the Applied Mathematics lab of Ecole Polytechnique; and INRIA Saclay, Platon team. I tried to accelerate CFD simulations using AI, which took me three full years to achieve.

After that, I looked for a job where I could **criterion 1:** live in the south of France, **criterion 2:** do ML research, **criterion 3:** in a topic not so far from my PhD, **criterion 4:** all that in a permanent position. I was lucky enough to join the [DEEL](https://www.deel.ai/) project in 2022, which was ticking every box. DEEL is a research project initiated in Toulouse by [IRT Saint Exupery](https://www.irt-saintexupery.com/fr/) in 2018, which became international in 2020 when the Canadian counterpart was created in Montreal, and part of Artificial and Natural Intelligence Toulouse Institute (ANITI), one of the four French institutes for AI research (3IA) launched in 2020. The research topics revolve around trustworthy AI: Explainable AI (XAI), Out-Of-Distribution (OOD) detection, Conformal Prediction, Robustness, Fairness,... At that time, the team was gaining momentum, with 5 papers accepted at NeuIPS (for a dozen core members). The year after I joined, we got 8!    

I quickly took the lead in the research effort on Out-Of-Distribution (OOD) detection and soon decided to try the open-source development experience with the creation of [Oodeel](https://github.com/deel-ai/oodeel), following the footsteps of [Xplique](https://github.com/deel-ai/xplique) and [Deel-lip](https://github.com/deel-ai/deel-lip) developed earlier by my teammates. In the meantime, I am still pursuing more classical research work.

Check out my research mindmap and reach out if interested in any topic!

<!-- pages/projects.md -->
<div class="projects">
{% if site.enable_project_categories and page.display_categories %}
  <!-- Display categorized projects -->
  {% for category in page.display_categories %}
  <a id="{{ category }}" href=".#{{ category }}">
    <h2 class="category">{{ category }}</h2>
  </a>
  {% assign categorized_projects = site.projects | where: "category", category %}
  {% assign sorted_projects = categorized_projects | sort: "importance" %}
  <!-- Generate cards for each project -->
  {% if page.horizontal %}
  <div class="container">
    <div class="row row-cols-1">
    {% for project in sorted_projects %}
      {% include projects_horizontal.liquid %}
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="grid">
    {% for project in sorted_projects %}
      {% include projects.liquid %}
    {% endfor %}
  </div>
  {% endif %}
  {% endfor %}

{% else %}

<!-- Display projects without categories -->

{% assign sorted_projects = site.projects | sort: "importance" %}

  <!-- Generate cards for each project -->

{% if page.horizontal %}

  <div class="container">
    <div class="row row-cols-1">
    {% for project in sorted_projects %}
      {% include projects_horizontal.liquid %}
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="grid">
    {% for project in sorted_projects %}
      {% include projects.liquid %}
    {% endfor %}
  </div>
  {% endif %}
{% endif %}
</div>
