---
layout: splash
title: Speakers
toc: true
---

<h1>Keynotes</h1>

<table>
{% tablerow x in site.data.speakers.keynote cols:2 %}
<center>
<img src="{{ x.image }}" style="height:200px;width:auto;"><br>
<a href="{{ x.website }}">{{ x.name }}</a><br>
{{ x.title }}<br>
{{ x.affiliation }}
</center>
<blockquote><strong>Title:</strong> {{ x.talk }}</blockquote>
{% endtablerow %}
</table>


<h1>Speakers</h1>

{% assign allspeakers = site.data.speakers.invited | concat: site.data.speakers.gt %}
{% assign allspeakers2 = allspeakers | sort: 'name' %}

<table>
{% tablerow x in allspeakers2 cols:3 %}
<div id="{{ x.name }}" style="text-align:center;">
<img src="{{ x.image }}" style="height:100px;width:auto;"><br>
<a href="{{ x.website }}">{{ x.name }}</a><br>
{{ x.title }}<br>
{{ x.affiliation }}
</div>
{% if x.talk %}
<blockquote><strong>Title:</strong> {{ x.talk }}</blockquote>
{% else %}
<blockquote><strong>Title:</strong> TBA</blockquote>

{% endif %}
{% endtablerow %}
</table>

<h1>Discussants</h1>

{% assign disc = site.data.speakers.discussants | sort: 'name' %}

<table>
{% tablerow x in disc cols:4 %}
<div id="{{ x.name }}" style="text-align:center;">
<img src="{{ x.image }}" style="height:100px;width:auto;"><br>
<a href="{{ x.website }}">{{ x.name }}</a><br>
{{ x.title }}<br>
{{ x.affiliation }}
</div>
{% endtablerow %}
</table>

