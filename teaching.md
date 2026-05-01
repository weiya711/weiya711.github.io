---
layout: page
title: Teaching
permalink: /teaching/
---

<table border="0">
{%- for teaching_keyval in site.data.teaching %}
  {%- assign teaching= teaching_keyval[1] -%}
  <tr>
  <td> 
    <b>
    {% if teaching.url %}
	<a href="{{teaching.url}}">{{teaching.title}}</a></b>
    {%- else %}
	{{teaching.title}}</b>
    {%- endif -%}
	<br/>{{teaching.month}} {{teaching.year}}, {{teaching.venue}}
  </td>
  </tr>
{% endfor %}
</table>
