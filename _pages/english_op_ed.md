---
layout: page
permalink: /english_op_ed/
title:
description: 
nav: true
nav_order: 6
---

<div class="post">

  {% assign blog_name_size = site.blog_name | size %}
  {% assign blog_description_size = site.blog_description | size %}

  {% if blog_name_size > 0 or blog_description_size > 0 %}
  <div class="header-bar">
    <h1>Op-Ed</h1>
    <h2>{{ site.blog_description }}</h2>
  </div>
  {% endif %}

  {% if site.display_tags or site.display_categories %}
  <div class="tag-category-list">
    <ul class="p-0 m-0">
      {% for tag in site.display_tags %}
        <!-- Filter out English ones  -->
        {%- if tag== "HK_Economic_Repositioning" or tag== "China" or tag== "Global_Economy" or tag== "HK_Reindustrialization" or tag== "International_Trade"   %}
            <li>
                <!-- <i class="fas fa-hashtag fa-sm"></i>  -->
                <a href="{{ tag | slugify | prepend: '/blog/tag/' | relative_url }}">{{ tag }}</a>
            </li>
            <!-- {% unless forloop.last %}
                <p>&bull;</p>
            {% endunless %} -->
        {% endif %}
      {% endfor %}
      <!-- {% if site.display_categories.size > 0 and site.display_tags.size > 0 %}
        <p>&bull;</p>
      {% endif %} -->
      
    </ul>
  </div>
  {% endif %}

</div>


<!-- Display projects without categories -->
{%- assign sorted_posts = site.posts | where: 'categories', 'English' -%}

<div class="row row-cols-1 row-cols-md-3 g-4">
  {%- for project in sorted_posts -%}
   <div class="card-body">
      <div class="card h-100" lang_used="English">
        <h2 class="card-title">{{ project.title }}</h2>
        <p class="card-text">{{ project.description }}</p>
        <p class="card-text">{{ project.date }}</p>
      </div>
    </div>
  {%- endfor %}
</div>
    

