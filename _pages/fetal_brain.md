---
title: "OMNI Lab - Characterising the Fetal Brain"
layout: gridlay
excerpt: "OMNI Lab -- Characterising the Fetal Brain."
sitemap: false
permalink: /fetal_brain/
---


# Characterising the Fetal Brain

Normal development of the human brain can be characterized by precisely timed growth and folding of its surface (cortex), with deviations often associated with poor cognitive outcomes. Advances in ultrasound (US) imaging technology now make it possible to visualize the cortex and screen for brain abnormalities before birth, from as early as 14 gestational weeks (GW). Working closely with the INTERGROWTH-21st Consortium and healthcare professionals, we develop a range of computational tools for assessing fetal health from US images.
---

{% assign number_printed = 0 %}
{% for publi in site.data.fetalpublist %}

{% assign even_odd = number_printed | modulo: 2 %}
{% if publi.highlight == 1 %}

{% if even_odd == 0 %}
<div class="row">
{% endif %}

<div class="col-sm-6 clearfix">
 <div class="row">
 	<img src="{{ site.url }}{{ site.baseurl }}/images/pubpic/{{ publi.image }}" class="img-responsive" width="30%" height="30%"  style="float: left" />
  <p><a class="pub1" href="{{ publi.link.url }}">{{ publi.title }}</a></p>
  <a class="pub2"> {{ publi.link.display }} </a>
 </div>
</div>

{% assign number_printed = number_printed | plus: 1 %}

{% if even_odd == 1 %}
</div>
{% endif %}

{% endif %}
{% endfor %}

{% assign even_odd = number_printed | modulo: 2 %}
{% if even_odd == 1 %}
</div>
{% endif %}

<p> &nbsp; </p>



