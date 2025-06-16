---
layout: splash
title: Agenda
toc: true
---
<script type="text/javascript"> 
function toggleBibtex(obj) { 
	var elems = document.body.getElementsByTagName("*");
	var i = 0;
	for (i =0; i < elems.length; i++) {
		var classname = elems[i].className;
		if (elems[i].id != obj && (classname == "talk" || classname == 'affil')) {
			elems[i].style.display = "none";
		}
	}
	element = document.getElementById(obj)
	if (element.style.display == "none") {
		element.style.display="block";
	}
	else {
		element.style.display="none";
	} 
	 

}
</script>

<style type="text/css" src="bibs.css">
.talkbutton {
	font-size: 8pt;
	background-color: black;
	color: white;
	border: 1px solid black;
	text-decoration: none;
	text-decoration-color: white;
	border-radius: 2px;
}
.talk {
	white-space: pre-wrap;
	background: #ffffff;
	color: red;
	border: 1px dotted red;
	width: 75%;
	position:absolute;
	overflow: hidden;
	z-index:2400;
	width: 250px;
}	
.affil {
	white-space: pre-wrap;
	background: #ffffff;
	color: blue;
	border: 1px dotted blue;
	width: 75%;
	position:absolute;
	overflow: hidden;
	z-index:2400;
	width: 250px;
}	
</style>

<h1>Agenda</h1>

The Summit takes place at the <a href="/location">Georgia Tech Global Learning Center</a> on the 2nd and 3rd floors.



<h1>Monday October 28th: Doctoral Consortium</h1>

The Doctoral Consortium will be held in the Georgia Tech Hotel, Conference Room A. It is connected to the Global Learning Center on the 2nd floor.

Please see the <a href="/doctoral-consortium">Doctoral Consortium</a> page for agenda.


<h1>Tuesday October 29th: Main Summit</h1>

{% assign allspeakers = site.data.speakers.invited | concat: site.data.speakers.gt | concat: site.data.speakers.keynote %}

<table width="100%" border=1 frame=void rules=rows>
	<tr><th>Time</th><th>Activity</th><th>Room 222</th><th>Room 330</th><th>Room 334</th></tr>
	{% for x in site.data.agenda.tuesday %}
		{% for y in x.slots %}
			<tr>
				<td>{{ y.time }}</td>
				<td>{{ y.activity }}</td>
				{% if y.tracks == nil %}
					<td>&nbsp;</td><td>&nbsp;</td><td>&nbsp;</td>
				{% else %}
					{% for z in y.tracks %}
						{% if y.activity contains "Discuss" %}
							<td><font style="font-size:10pt;">Discussant: {{ z.name }}</font></td>
						{% else %}
							{% assign r = allspeakers | where:"name", z.name | first %}
							<td><a href="/speakers/index.html#{{z.name}}">{{ z.name }}</a>
							{% assign n = z.name | smartify%}
							<a onclick="toggleBibtex('{{ n }} bio');"><span class="talkbutton">bio</span></a><div class="affil" id="{{ n }} bio" style="display: none;">{{ r.title }}, {{ r.affiliation }}</div>
							{% if r.talk != nil %}
								<a onclick="toggleBibtex('{{ n }} talk');"><span class="talkbutton">talk</span></a><div class="talk" id="{{ n }} talk" style="display: none;">{{ r.talk }}</div>
							{% endif %}
							{% if y.activity contains "Keynote" %}
								<br><font style="font-size:10pt;">Discussant: {{ y.discussant }}</font>
							{% endif %}							
							</td>
						{% endif %}
					{% endfor %}
				{% endif %}
			</tr>
		{% endfor %}
	{% endfor %}
</table>



<h1>Wednesday October 30th: Main Summit</h1>

<table width="100%" border=1 frame=void rules=rows>
	<tr><th>Time</th><th>Activity</th><th>Room 222</th><th>Room 330</th></tr>
	{% for x in site.data.agenda.wednesday %}
		{% for y in x.slots %}
			<tr>
				<td>{{ y.time }}</td>
				<td>{{ y.activity }}</td>
				{% if y.tracks == nil %}
					<td>&nbsp;</td><td>&nbsp;</td><td>&nbsp;</td>
				{% else %}
					{% for z in y.tracks %}
						{% if y.activity contains "Discuss" %}
							<td><font style="font-size:10pt;">Discussant: {{ z.name }}</font></td>
						{% else %}
							{% assign r = allspeakers | where:"name", z.name | first %}
							{% assign bar = foo.talk %}
							<td><a href="/speakers/index.html#{{z.name}}">{{ z.name }}</a>
							{% assign n = z.name | smartify%}
							<a onclick="toggleBibtex('{{ n }} bio');"><span class="talkbutton">bio</span></a><div class="affil" id="{{ n }} bio" style="display: none;">{{ r.title }}, {{ r.affiliation }}</div>
							{% if r.talk != nil %}
								<a onclick="toggleBibtex('{{ n }} talk');"><span class="talkbutton">talk</span></a><div class="talk" id="{{ n }} talk" style="display: none;">{{ r.talk }}</div>
							{% endif %}
							{% if y.activity contains "Keynote" %}
								<br><font style="font-size:10pt;">Discussant: {{ y.discussant }}</font>
							{% endif %}
							</td>
						{% endif %}
					{% endfor %}
				{% endif %}

			</tr>
		{% endfor %}
	{% endfor %}
</table>

