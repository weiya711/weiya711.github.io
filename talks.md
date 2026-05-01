---
layout: page
title: Talks
permalink: /talks/
---

<table border="0">
{%- for talk_keyval in site.data.talks %}
  {%- assign talk= talk_keyval[1] -%}
  <tr>
  <td> 
    <b>
    {% if talk.url %}
	<a href="{{talk.url}}">{{talk.title}}</a></b>
    {%- else %}
    {{talk.title}}</b>
    {%- endif -%}
	<br/>{{talk.month}} {{talk.year}} 
    <br/>{{talk.venue}}
    <td valign="top" width="20">
    {% if talk.movie %}
      <a href="{{ talk.movie }}"><img src="/assets/movie.png" alt="youtube" /></a>
    {% endif %}
    </td>
  </td>
  </tr>
{% endfor %}
</table>
