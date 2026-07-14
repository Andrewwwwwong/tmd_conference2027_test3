---
layout: page
title: Invited Speakers
alt_title: Confirmed Invited Speakers
permalink: /speakers/
---

<div class="entries-grid">
{% for pair in site.data.2D_Conference %}

	<article class="portrait">
		<img src="{{ '/assets/Invited Speakers/Accepted/' | relative_url }}{{ pair['Name'] }}.jpg" class="portrait">
        <b>{{ pair["Name"] }}</b>
        <em>{{ pair["Institute"] }}</em>
	</article>

{% endfor %}
</div>
