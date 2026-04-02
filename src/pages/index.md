---
layout: base
permalink: /index.html
title: 'giga jobless WIP site'
description: 'Eleventy starter using modern CSS, fluid type, fluid spacing, flexible layout and progressive enhancement.'
blog:
  title: 'Blog'
  intro: "I'm showing the last 4 blog posts, but there might be more!"
---

<div class="wrapper">
  <header class="full | section" style="--spot-color: var(--color-primary)">
    <div class="section__inner flow region">
      <h1 class="text-center" style="color: var(--color-light);">{{ title }}</h1>
    </div>
    {% svg "divider/waves", null, "divider" %}
  </header>

  <article class="full | region">
    <div class="prose wrapper flow">
      <h2 id="an-eleventy-starter">Do Not Go Gentle into That Good Night</h2>

      Do not go gentle into that good night,
      Old age should burn and rave at close of day;
      Rage, rage against the dying of the light.
      
      Though wise men at their end know dark is right,
      Because their words had forked no lightning they
      Do not go gentle into that good night.
      
      Good men, the last wave by, crying how bright
      Their frail deeds might have danced in a green bay,
      Rage, rage against the dying of the light.
      
      Wild men who caught and sang the sun in flight,
      And learn, too late, they grieved it on its way,
      Do not go gentle into that good night.
      
      Grave men, near death, who see with blinding sight
      Blind eyes could blaze like meteors and be gay,   
      Rage, rage against the dying of the light.
      
      And you, my father, there on the sad height,
      Curse, bless, me now with your fierce tears, I pray.
      Do not go gentle into that good night.
      Rage, rage against the dying of the light.
      


  <section class="full | region">
    <div class="prose wrapper flow">
      <h2>{{ blog.title }}</h2>

      {% if blog.intro %}
        <p>{{ blog.intro }}</p>
      {% endif %}

      <div class="feature | region region-space-l">
        <custom-masonry layout="50-50">
          {% set itemList = collections.allPosts %}
          {% asyncEach item in itemList.slice(0, 4) %}
            {% set headingLevel = "h3" %}
            {% include "partials/card-blog.njk" %}
          {% endeach %}
        </custom-masonry>
      </div>
    </div>
  </section>
</div>
