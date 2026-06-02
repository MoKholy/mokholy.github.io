---
title: "Publications"
layout: single
permalink: /publications/
author_profile: true
---

{% assign publications = site.publications | sort: "date" | reverse %}
{% assign current_year = "" %}
{% assign pub_index = 0 %}

{% for pub in publications %}
{% assign pub_year = pub.date | date: "%Y" %}

{% if pub_year != current_year %}
{% assign current_year = pub_year %}
{% assign pub_index = 0 %}

## {{ current_year }}
{% endif %}

{% assign pub_index = pub_index | plus: 1 %}

<div class="publication-entry">
  <div class="publication-number">[{{ pub_index }}]</div>
  <div class="publication-content">
    <div class="publication-title">
      {{ pub.title }}
    </div>
    <div class="publication-authors">
      {% for author in pub.authors %}{% if author == site.scholar_name %}<strong>{{ author }}</strong>{% else %}{{ author }}{% endif %}{% unless forloop.last %}, {% endunless %}{% endfor %}
    </div>
    {% if pub.venue %}
    <div class="publication-venue">
      {{ pub.venue }}
    </div>
    {% endif %}
    <div class="publication-links">
        {% if pub.paperurl %}<a href="{{ pub.paperurl }}" target="_blank"><i class="far fa-file-pdf"></i> Paper</a>{% endif %}
        {% if pub.codeurl %} · <a href="{{ pub.codeurl }}" target="_blank"><i class="fab fa-github"></i> Code</a>{% endif %}
        {% if pub.posterurl %} · <a href="{{ pub.posterurl }}" target="_blank"><i class="fas fa-image"></i> Poster</a>{% endif %}
        {% if pub.slidesurl %} · <a href="{{ pub.slidesurl }}" target="_blank"><i class="fas fa-chalkboard"></i> Slides</a>{% endif %}
        {% if pub.websiteurl %} · <a href="{{ pub.websiteurl }}" target="_blank"><i class="fas fa-globe"></i> Project</a>{% endif %}
    </div>
    {% if pub.excerpt %}
    <div class="publication-abstract">
      {{ pub.excerpt }}
    </div>
    {% endif %}
  </div>
</div>

{% endfor %}