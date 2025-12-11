---
layout: page
title: projects
permalink: /projects/
description: A growing collection of your cool projects.
nav: false
nav_order: 2
display_categories: [work, fun]
horizontal: false
---
We are the **Cosmology with Statistical Inference (CSI)** research group at **IIT Indore**.

Our research focuses on understanding the **evolutionary history of the Universe**, especially the period when the **first stars and galaxies** formed, known as the **Cosmic Dawn (CD)** — and the subsequent transformation of the intergalactic medium from neutral to ionized during the **Epoch of Reionization (EoR)**.

We are particularly interested in extracting physical information from observations of the **redshifted 21-cm signal**, large-scale structure tracers, and multi-wavelength astrophysical surveys. Our work involves developing and applying statistical, computational, and inference-driven techniques to interpret data and connect observations with theoretical models of the early Universe.

To achieve these goals, we work with data from current radio interferometers such as **GMRT, LOFAR, MWA**, and **PAPER**, as well as preparing for science with the upcoming **Square Kilometre Array (SKA)**. We also explore synergies with telescopes across optical, infrared, and X-ray bands, including **Euclid, Athena, WFIRST, JWST, ELT, TMT, SPHEREx, TIME,** and **CONCERTO**, among others.

These combined observations and statistical approaches will open a **new window into the early stages of cosmic structure formation**, helping us better understand how the first luminous sources shaped the Universe we observe today.
<!--
Link to your social media connections, too. This theme is set up to use [Font Awesome icons](https://fontawesome.com/) and [Academicons](https://jpswalsh.github.io/academicons/), like the ones below. Add your Facebook, Twitter, LinkedIn, Google Scholar, or just disable all of them.
profile:
  align: right
  image: prof_pic.jpg
  image_circular: false # crops the image to make it circular
  more_info: ""

-->
Some of the projects goes here....
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
    <div class="row row-cols-1 row-cols-md-2">
    {% for project in sorted_projects %}
      {% include projects_horizontal.liquid %}
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="row row-cols-1 row-cols-md-3">
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
    <div class="row row-cols-1 row-cols-md-2">
    {% for project in sorted_projects %}
      {% include projects_horizontal.liquid %}
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="row row-cols-1 row-cols-md-3">
    {% for project in sorted_projects %}
      {% include projects.liquid %}
    {% endfor %}
  </div>
  {% endif %}
{% endif %}
</div>
