---
layout: page
title: Gallery
permalink: /gallery/
description: 
nav: true
nav_order: 3
display_categories: [Cities, Universities, Miscellaneous]
horizontal: false
---
John F. Nash, Jr. kept an online album of photos. These can be found today on <a href="https://web.math.princeton.edu/jfnj/">his web page</a>. They range from a photo of the <a href="https://web.math.princeton.edu/jfnj/texts_and_graphics/Mezzanine.Directory/Transfer.Elevator.and.Photos/Photos/Oxford.photo.jpgs.2014/saved.Oxford.visit.group.downloaded.2014.512.1151AM%20089.jpg">Bodleian Library</a> to just <a href="https://web.math.princeton.edu/jfnj/texts_and_graphics/Mezzanine.Directory/Transfer.Elevator.and.Photos/Photos/Photos_from_Campus_for_Finance_Vallendar_2010/2010_01_13/IMG_0514.JPG">some random stairs</a>. Another mathematician who liked to take photos was Paul R. Halmos. From the 6000 or so photographs in his collection, Halmos chose about 600 for his book "I Have a Photographic Memory."

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
