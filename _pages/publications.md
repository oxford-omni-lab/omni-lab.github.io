---
title: "OMNI Lab - Publications"
layout: gridlay
excerpt: "OMNI Lab -- Publications."
sitemap: false
permalink: /publications/
---


# Publications

---

## Featured

{% assign number_printed = 0 %}
{% for publi in site.data.publist %}

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

---
## Recent Publications

{% assign number_printed = 0 %}
{% for publi in site.data.publist %}

{% assign even_odd = number_printed | modulo: 2 %}
{% if publi.highlight == 2 %}

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

---

## Publications by theme

[Characterising the Fetal Brain]({{ site.url }}{{ site.baseurl }}/fetal_brain) / [⁠⁠2D-3D US Reconstruction]() /  ⁠⁠[Clinical Translation]() /  [⁠⁠Deep Learning Methodology]()

---

<div>
## Full List

For a full list, please go to <a class="regtext" href="https://scholar.google.com/citations?user=6QzRJ6MAAAAJ">Google Scholar</a> or <a class="regtext" href="https://pubmed.ncbi.nlm.nih.gov/?term=Namburete+AIL%5BAuthor%5D">Pubmed</a>.
<br><br><br>

</div>
