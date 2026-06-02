---
title: "Publications"
layout: single
permalink: /publications/
author_profile: true
---

# Publications

{% assign publications = site.publications | sort: "date" | reverse %}
{% assign current_year = "" %}

{% for pub in publications %}

{% assign pub_year = pub.date | date: "%Y" %}

{% if pub_year != current_year %}
{% assign current_year = pub_year %}
## {{ current_year }}
{% endif %}

### {{ pub.title }}

{% for author in pub.authors %}
{% if author == site.scholar_name %}
<strong>{{ author }}</strong>{% else %}{{ author }}{% endif %}{% unless forloop.last %}, {% endunless %}
{% endfor %}

{% if pub.venue %}
  
*{{ pub.venue }}*

{% endif %}

{% assign links = "" %}

{% if pub.paperurl %}
[Paper]({{ pub.paperurl }})
{% endif %}
{% if pub.codeurl %}
 | [Code]({{ pub.codeurl }})
{% endif %}
{% if pub.slidesurl %}
 | [Slides]({{ pub.slidesurl }})
{% endif %}
{% if pub.posterurl %}
 | [Poster]({{ pub.posterurl }})
{% endif %}
{% if pub.websiteurl %}
 | [Project Page]({{ pub.websiteurl }})
{% endif %}

{% if pub.excerpt %}
  
{{ pub.excerpt }}

{% endif %}

---

{% endfor %}