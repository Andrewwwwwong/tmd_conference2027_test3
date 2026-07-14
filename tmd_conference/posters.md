---
layout: page
permalink: /posters/
title: Poster Program
---


<table>
	<tr>
		<th>Poster</th>
		<th>Info</th>
	</tr>
	{% for item in site.data.Posters_program %}
	<tr class="top-aligned">
		<td class="time-row"><b>{{ item.ID }}</b></td>
		<td>
			{% include talkInfo.html time="Tuesday, 17:30 - 21:00" room="Concourse" num=forloop.index0 speaker=item.Name title=item.Title abstract=item.Abstract affiliation=item.Affiliation %}
		</td>
	</tr>
	{% endfor %}
</table>

{% include talkInfoJS.html %}
