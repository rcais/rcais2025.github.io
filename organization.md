---
layout: splash
title: Organization
toc: true
---

<h1>Organizing Committee:</h1>

{% for x in site.data.organization.members %}
  <p>
    <img src="{{ x.image }}" width="100">
    <a href="{{ x.website }}">{{ x.name }}</a>, {{ x.title }}, {{ x.affiliation }}
  </p>
{% endfor %}

<h1>Student Volunteers</h1>

{% for x in site.data.organization.volunteers %}
  <p>
    {% if x.image %}
    <img src="{{ x.image }}" width="100">
    {% endif %}
    {{ x.name }}, {{ x.title }}, {{ x.affiliation }}
  </p>
{% endfor %}

<h1>Staff Miracle Workers</h1>

{% for x in site.data.organization.staff %}
  <p>
    {% if x.image %}
    <img src="{{ x.image }}" width="100">
    {% endif %}
    {{ x.name }}, {{ x.title }}, {{ x.affiliation }}
  </p>
{% endfor %}
