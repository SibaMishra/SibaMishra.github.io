---
layout: page
title: All News
permalink: /news/
navinclude: false
---
{: style="text-align: justify"}
<div class="allnews">
  {% if site.news %}
    <table>
    {% assign news = site.news | sort: 'date' | reverse %}
    {% for item in news%}
      <tr>
        <td class="date">{{ item.date | date: "%b %-d, %Y" }}</td>
        <td class="announcement">
          {% if item.inline %}
            {{ item.content | remove: '<p>' | remove: '</p>' | emojify }}
          {% else %}
            <a class="news-title" href="{{ item.url | prepend: site.baseurl }}"><small>{{ item.title | emojify }}</small></a>
          {% endif %}
        </td>
      </tr>
    {% endfor %}
    </table>
  {% else %}
    <p>No news so far...</p>
  {% endif %}
</div>
