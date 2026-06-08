---
layout: page
title: Research Projects
permalink: /projects/
description: 
nav: true
nav_order: 3
display_categories: [work]
horizontal: false
---

We collaborate closely with neurosurgeons Dr. Christopher Graffeo and Dr. Andrew Bauer and neuroscientists Dr. Anna Csiszar and Dr. Stefano Tarantini at the OU Health Science Center (HSC) Department of Neurosurgery, which ranked #14 for NIH funding in 2023 among Neurosurgery Departments.

We also collaborate closely with the Stephenson Cancer Center (SCC) at OU HSC. The SCC is a National Cancer Institute designated cancer center and is the nation’s No. 1 cancer center for patient clinical trial accrual.

Funding sources include: <br>
* National Institutes of Health (NIH) Centers of Biomedical Research Excellence (COBRE) for “Neuroimaging-guided Immunotherapy for Glioblastoma.” (PI: Miller)
* National Science Foundation (NSF) Seed Translational Research Project (STRP) for “Machine Learning for Real-time Detection of Complications during Neurosurgery.” (PI: Miller)
* OK BioStart for "Clinical Translational Research in Augmented Reality for Neuronavigation" (PIs: Miller / Potts)
* American Cancer Society (ACS) Institutional Research Grant Pilot for "Intraoperative Surgical Guidance During Resection of Brain Tumors" (PI: Miller)
* Presbyterian Health Foundation (PHF) Technology Advancement Grant (TAG) for "Seeing Deeper: Three-photon microscopy for deep-tissue mouse brain imaging" (PIs: Csiszar / Miller)


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
