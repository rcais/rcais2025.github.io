---
layout: splash
title: Doctoral Consortium
toc: true
---

<h1>Doctoral Consortium</h1>

The Doctoral Consortium on Responsible Computing, AI, and Society will be held on October 28th in the Georgia Tech Hotel on Georgia Tech campus, Conference Room A.

The Doctoral Consortium will provide opportunities to receive mentorship on the crucial issues navigating research in responsible computing, AI, and policy.

<h1>Schedule</h1>

The Doctoral Consortium will be held in the Georgia Tech Hotel, Conference Room A.

| Time | Activity | 
|------|----------|
{% for x in site.data.agenda.monday -%}
{%- for y in x.slots -%}
| {{ y.time }} | {{ y.activity }} | 
{% endfor %}
{% endfor %} 

<h1>Participants</h1>

{% assign participants = site.data.dc.participants | sort: 'name' %}

<table>
{% tablerow x in participants cols: 3 %}
<div id="{{ x.name }}" style="text-align:center;">
{% if x.image %}
<img src="{{ x.image }}" style="height:200px;width:auto;"><br>
{% endif %}
<a href="{{ x.website }}">{{ x.name }}</a><br>
{{ x.affiliation }}
</div>
{% endtablerow %}
</table>

<h1>Mentors and Panelists</h1>

{% assign mentors = site.data.dc.mentors | sort: 'name' %}

<ul>
  {% for x in mentors %}
  <li><a href="{{ x.website}} ">{{ x.name }}</a>, {{ x.title }}, {{ x.affiliation }}</li>
  {% endfor %}
</ul>



