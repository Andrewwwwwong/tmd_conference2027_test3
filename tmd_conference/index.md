---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: home
title: 2D Transition Metal Dichalcogenides 2027
sub_title: June 27 - July 1, 2027 | Churchill College, Cambridge, UK
image: /assets/top_banner.jpg
introduction: |
  Following successful 2D TMDs conferences in Cambridge and Hong Kong, we will be holding the 2D TMDs 2025 conference in Cambridge again. The conference will again gather leading researchers from academia and industry to present and discuss cutting-edge research in the field of atomically thin TMDs and related materials. The conference will cover latest developments in synthesis of 2D TMDs and their implementation in electronics, photonics, catalysis, as well as energy conversion and storage. <b>Abstracts from students and postdoctoral researchers are very welcome.</b>
---
## Topics

Topics will include but are not limited to:

<div class="topics-grid">
	<div>
	  <ul>
		{% for topic in site.data.topics limit:4 %}
		<li>
			{{ topic['name'] }}
		</li>
		{% endfor %}
  	  </ul>
	</div>
	<div>
	<ul>
		{% for topic in site.data.topics offset:4 %}
		<li>
			{{ topic['name'] }}
		</li>
		{% endfor %}
	</ul>
	</div>
</div>


## Confirmed Plenary Speakers 

To be Confirmed.

{% comment %}

<div class="entries-grid">
{% for pair in site.data.plenaries %}

	<article class="portrait">
		<img src="{{ '/assets/Plenary Speakers/' | relative_url }}{{ pair['Name'] }}.jpg" class="portrait">
        <b>{{ pair["Name"] }}</b>
        <em>{{ pair["Institute"] }}</em>
	</article>
{% endfor %}
</div>

{% endcomment %}

## Organizers

To be Confirmed.

{% comment %}

<div class="speaker-box">
{% for pair in site.data.organizers %}

	<article class="portrait">
		<img src="{{ '/assets/organizers/' | relative_url }}{{ pair['Name'] }}.jpg" class="portrait">
        <b>{{ pair["Name"] }}</b>
        <em>{{ pair["Institute"] }}</em>
	</article>
{% endfor %}
</div>

{% endcomment %}

## Co-organizers

To be Confirmed.

{% comment %}

<div class="speaker-box">
{% for pair in site.data.co-organizers %}

	<article class="portrait">
		<img src="{{ '/assets/co-organizers/' | relative_url }}{{ pair['Name'] }}.jpg" class="portrait">
        <b>{{ pair["Name"] }}</b>
        <em>{{ pair["Institute"] }}</em>
	</article>
{% endfor %}
</div>

To be Confirmed.

{% endcomment %}

## Sponsors

To be Confirmed.

{% comment %}

{% assign sponsors = "HenryRoyceInstitute.png;Aixtron.svg;molyon.png;weboftalents.png;RoyceCambridgelogo.jpg;APLEnergyElectronicslogo.jpg;Linkzilllogo.jpg;HeidelbergInstruments.png;Qlibri.png;nature materials.png;qamss.png" | split: ";"  %}


<div class="tmd-sponsors">
	{% for logoName in sponsors %}
	<article class="tmd-sponsors">
		<img src="{{ '/assets/sponsors/' | relative_url }}{{logoName}}" class="logo">
	</article>
	{% endfor %}
</div>

{% endcomment %}
