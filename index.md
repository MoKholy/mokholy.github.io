---
# You don't need to edit this file, it's empty on purpose.
# Edit theme's home layout instead if you wanna make some changes
# See: https://jekyllrb.com/docs/themes/#overriding-theme-defaults
layout: single
author_profile: true
---

I am a Research Engineer at the [AramLab](https://aramlab.ai/) @ MBZUAI, I am also an incoming PhD student @ MBZUAI, working under the supervision of [Bashar Alhafni](https://www.basharalhafni.com/). I currently work on Arabic NLP.

## Research Interests
- Interpretability
- Representation Learning
- Training dynamics

## News

<div class="news-list"> 
    {% assign news_items = site.data.news | default: empty | sort: "date" | reverse %} 
    {% for item in news_items limit: 5 %} 
    <div class="news-item"> 
        <span class="news-date"> 
            {{ item.date | date: "%b %Y" }} 
        </span> 
        <span class="news-title"> 
            {% if item.url %} {{ item.prefix }} 
                <a href="{{ item.url }}" target="_blank"> 
                    {{ item.link_text }} 
                </a> 
            {% else %} 
                {{ item.title }} 
            {% endif %} 
        </span> 
    </div> 
    {% endfor %}
</div>