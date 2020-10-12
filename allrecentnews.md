---
layout: page
title: All News
permalink: /news/
navinclude: false
text-align: justify !important
---
<div class="allnews">
  {% if site.news %}
  <div>
    <table>
    {% assign news = site.news | sort: 'date' | reverse %}
    {% for item in news%}
      <tr>
        <td class="date"><small>{{ item.date | date: "%b %-d, %Y" }}</small></td> 
        <td class="announcement">
          {% if item.inline %}
          <small>{{ item.content | remove: '<p>' | remove: '</p>' | emojify }}</small>
          {% else %}
            <a class="news-title" href="{{ item.url | prepend: site.baseurl }}"><small>{{ item.title | emojify }}</small></a>
          {% endif %}
        </td>
      </tr>
    {% endfor %}
    </table>
  </div>
  {% else %}
    <p> No news so far... </p>
  {% endif %}
</div>
