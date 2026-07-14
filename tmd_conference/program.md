---
layout: page
title: Program
permalink: /program/
---
{% comment %}
<article class="entry" style="text-align: center;">
    <img src="{{ '/assets/hotels/20th July.png' | relative_url  }}" width="1000" >
</article>

<article class="entry" style="text-align: center;">
    <img src="{{ '/assets/hotels/21st July first2.png' | relative_url  }}" width="1000">
</article>

<article class="entry" style="text-align: center;">
    <img src="{{ '/assets/hotels/21st July second2.png' | relative_url  }}" width="1000">
</article>

<article class="entry" style="text-align: center;">
    <img src="{{ '/assets/hotels/22nd July first2.png' | relative_url  }}" width="1000">
</article>

<article class="entry" style="text-align: center;">
    <img src="{{ '/assets/hotels/22nd July second2.png' | relative_url  }}" width="1000">
</article>

<article class="entry" style="text-align: center;">
    <img src="{{ '/assets/hotels/23rd July first2.png' | relative_url  }}" width="1000">
</article>

<article class="entry" style="text-align: center;">
    <img src="{{ '/assets/hotels/23rd July second2.png' | relative_url  }}" width="1000">
</article>

<article class="entry" style="text-align: center;">
    <img src="{{ '/assets/hotels/24th July first2.png' | relative_url  }}" width="1000">
</article>

<article class="entry" style="text-align: center;">
    <img src="{{ '/assets/hotels/24th July second2.png' | relative_url  }}" width="1000">
</article>


To be confirmed.



{% assign days = "Sunday;Monday;Tuesday;Wednesday;Thursday" | split: ";" %}

<div style="display:flex;flex-wrap:wrap">
	<div style="flex: 1 0">
		<h2>Quicklinks:</h2>

		<div class="program-menu">
			{% for day in days %}
			<a class="menu-item program-menu-item" href="#{{ day | downcase }}"><div class="menu-item program-menu-item">{{ day }}</div></a>
			{% endfor %}
			<a class="menu-item program-menu-item" href="{{ '/posters/' | relative_url }}"><div class="menu-item program-menu-item">Poster Session Program</div></a>
		</div>
	</div>
	<div style="flex: 0 0 400px">
		<h2>Latest Updates:</h2>

		<div class="twitter-feed">
			<a class="twitter-timeline" data-height="300px" href="https://x.com/2D_TMDs_2025">2D_TMDs_2025</a> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script> 
		</div>
	</div>
</div>

{% assign talkCountP = 0 %}
{% assign talkCountA = 0 %}
{% assign talkCountB = 0 %}
{% assign talkCountC = 0 %}
{% assign talkCountD = 0 %}

{% for day in days %}

## {{ day }}

<table>
	{% assign data_file = day | append: "_program" %}
	
	{% for item in site.data[data_file] %}
	{% capture day_time %}
	{{ day }}, {{ item.Time }}
	{% endcapture %}
	
	<tr class="top-aligned">
	<td class="time-row"><b>{{ item.Time }}</b></td>
	{% case item.Type %}
		{% when "Rooms" %}
			{% include roomRow.html roomA=item.RoomA roomB=item.RoomB roomC=item.RoomC roomD=item.RoomD %}
		{% when "Breakfast", "Coffee", "Lunch", "Dinner", "Meal" %}
			{% include mealRow.html text=item.Text type=item.Type room=item.RoomA %}
		{% when "Plenary", "Editoral Session" %}
			{% include pleanaryRow.html num=talkCountP time=day_time room=item.RoomA text=item.Text speaker=item.SpeakerA title=item.TitleA abstract=item.AbstractA affiliation=item.AffiliationA %}
			{% assign talkCountP = talkCountP | plus: 1 %}
		{% when "Invited" %}
			{% include speakerRow.html time=day_time
									   numA=talkCountA speakerA=item.SpeakerA titleA=item.TitleA abstractA=item.AbstractA affiliationA=item.AffiliationA roomA=item.RoomA
									   numB=talkCountB speakerB=item.SpeakerB titleB=item.TitleB abstractB=item.AbstractB affiliationB=item.AffiliationB roomB=item.RoomB
									   numC=talkCountC speakerC=item.SpeakerC titleC=item.TitleC abstractC=item.AbstractC affiliationC=item.AffiliationC roomC=item.RoomC
									   numD=talkCountD speakerD=item.SpeakerD titleD=item.TitleD abstractD=item.AbstractD affiliationD=item.AffiliationD roomD=item.RoomD %}
			
			{% assign talkCountA = talkCountA | plus: 1 %}
			{% assign talkCountB = talkCountB | plus: 1 %}
			{% assign talkCountC = talkCountC | plus: 1 %}
			{% assign talkCountD = talkCountD | plus: 1 %}

		{% when "Chairs" %}
			{% include chairsRow.html speakerA=item.SpeakerA affiliationA=item.AffiliationA
									   speakerB=item.SpeakerB affiliationB=item.AffiliationB
									   speakerC=item.SpeakerC affiliationC=item.AffiliationC
									   speakerD=item.SpeakerD affiliationD=item.AffiliationD %}

		{% when "Poster Session" %}
			{% include posterRow.html %}
		{% else %}
			{% include mealRow.html text=item.Text type=item.Type room=item.RoomA %}
	{% endcase %}
	</tr>
	{% endfor %}
</table>
{% endfor %}

{% include talkInfoJS.html %}

{% endcomment %}

