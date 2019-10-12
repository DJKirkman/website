---
title: "Partners"
---

Here at CompSoc we are supported by some great companies that are passionate about engaging in student life.
We are eternally grateful for their support over the years.

{% for group in site.data.partners %}
<div class="partners">
	{% for partner in group %}
		{% assign imgStart = partner.img | slice: 0, 4 %}
		{% assign img = partner.img %}
		{% capture width %}{% if partner.maxwidth %} style="max-width: {{ partner.maxwidth }}" {% endif %}{% endcapture %}

		{% unless imgStart == "http" %}
			{% capture img %}{{ site.baseurl }}/{{ img }}{% endcapture %}
		{% endunless %}

		{% unless partner.url == "" %}
			<a href="{{ partner.url}}" {{ width }}>
		{% endunless %}
				<img src="{{ img }}" {{ width }}>
		{% unless partner.url == "" %}
			</a>
		{% endunless %}
	{% endfor %}
</div>
{% endfor %}

<div class="mt-5 pt-5">
	<center>This year we also have a partnered pub, Revolution!</center>
	<div class="partners mt-0">
		<a href="https://www.revolution-bars.co.uk/bar/edinburgh/"><img src="{{ site.baseurl }}/static/img/partners/revolution.svg" style="min-width: 150px; max-width: 500px"></a>
	</div>
</div>
