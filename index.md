---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: home
---

{%- for city in site.data.cities -%}
<label>{{city.name}}</label>
<ul>
{%- assign locations = site.data.locations | where: 'city', city.name -%}
{%- if locations.size > 0 -%}
	{%- for location in locations -%}
	<li>
		<a href="{{location.url}}" target="_blank">{{location.name}}</a>
	</li>
	{%- endfor -%}
{%- else -%}
	<li>No Locations Known</li>
{%- endif -%}
</ul>
{%- endfor -%}