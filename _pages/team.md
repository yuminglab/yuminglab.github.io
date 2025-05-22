---
title: "Team"
layout: gridlay
sitemap: false
permalink: /team/
---

## Team

**We are looking for new team members** [(see openings)]({{ site.url }}{{ site.baseurl }}/vacancies) **!**

[//]: # (## PI)

[//]: # ({% for member in site.data.pi %})

[//]: # ()
[//]: # (<div class="jumbotron">)

[//]: # (<div class="row">)

[//]: # (<div class="col-sm-2">)

[//]: # (  <img src="{{ site.url }}{{ site.baseurl }}/images/{{ member.photo }}" width="100%" style="max-width:250px"/>)

[//]: # (</div>)

[//]: # (<div class="col-sm-9 col-xs-12">)

[//]: # (<h4>{{ member.name }}</h4>)

[//]: # (<i>{{ member.info }}</i><br>)

[//]: # ()
[//]: # ({% if member.website %}<a href="{{ member.website }}" target="_blank"><i class="fa fa-home fa-2x"></i></a> {% endif %} {% if member.email %}<a href="mailto:{{ member.email }}" target="_blank"><i class="fa fa-envelope-square fa-2x"></i></a> {% endif %} {% if member.scholar %} <a href="{{ member.scholar }}" target="_blank"><i class="ai ai-google-scholar-square ai-2x"></i></a> {% endif %} {% if member.cv %} <a href="{{ member.cv }}" target="_blank"><i class="ai ai-cv-square ai-2x"></i></a> {% endif %} {% if member.github %} <a href="{{ member.github }}" target="_blank"><i class="fa fa-github-square fa-2x"></i></a> {% endif %} {% if member.researchgate %} <a href="{{ member.researchgate }}" target="_blank"><i class="ai ai-researchgate-square ai-2x"></i></a> {% endif %})

[//]: # ()
[//]: # (<ul style="overflow: hidden">)

[//]: # (<li> {{ member.education[0] }} </li>)

[//]: # (<li> {{ member.education[1] }} </li>)

[//]: # (</ul>)

[//]: # (</div>)

[//]: # (</div>)

[//]: # (</div>)

[//]: # ()
[//]: # ({% endfor %})

## Current Students and Postdocs

<div class='jumbotron'>
{% assign number_printed = 0 %}
{% for member in site.data.team_members %}

{% assign even_odd = number_printed | modulo: 2 %}

{% if even_odd == 0 %}

<div class="row">
{% endif %}

<div class="col-sm-2">
<img src="{{ site.url }}{{ site.baseurl }}/images/{{ member.photo }}" width="100%" style="max-width:250px; border-radius: 50%;"/>
</div>
<div class="col-sm-4 col-xs-12">
  <h4>{{ member.name }}</h4>
  <i>{{ member.info }}<br></i>
<div class="social-icons mt-2">
{% if member.website %}<a href="{{ member.website }}" target="_blank"><i class="fa fa-home fa-2x"></i></a> {% endif %}
{% if member.email %}<a href="mailto:{{ member.email }}" target="_blank"><i class="fa fa-envelope-square fa-2x"></i></a> {% endif %}
{% if member.scholar %} <a href="{{ member.scholar }}" target="_blank"><i class="ai ai-google-scholar-square ai-2x"></i></a> {% endif %}
{% if member.cv %} <a href="{{ member.cv }}" target="_blank"><i class="ai ai-cv-square ai-2x"></i></a> {% endif %}
{% if member.github %} <a href="{{ member.github }}" target="_blank"><i class="fa fa-github-square fa-2x"></i></a> {% endif %}
{% if member.researchgate %} <a href="{{ member.researchgate }}" target="_blank"><i class="ai ai-researchgate-square ai-2x"></i></a> {% endif %}
{% if member.linkedin %}<a href="{{ member.linkedin }}" target="_blank"><i class="fa fa-linkedin-square fa-2x"></i></a> {% endif %}
</div>
</div>
<!-- </div> -->

{% assign number_printed = number_printed | plus: 1 %}

{% if even_odd == 1 %}

</div>
{% endif %}

{% endfor %}

{% assign even_odd = number_printed | modulo: 2 %}
{% if even_odd == 1 %}

</div>
{% endif %}
</div>

## Alumni

<div class="jumbotron">

{% assign number_printed = 0 %}

{% for member in site.data.alumni %}


{% assign even_odd = number_printed | modulo: 2 %}


{% if even_odd == 0 %}


<div class="row">
{% endif %}


<div class="col-sm-2">

<img src="{{ site.url }}{{ site.baseurl }}/images/{{ member.photo }}" width="100%" style="max-width:250px; border-radius: 50%;"/>

</div>

<div class="col-sm-4 col-xs-12">

  <h4>{{ member.name }}</h4>

  <i>{{ member.duration }} <br> Role: {{ member.info }}</i>

<div class="social-icons mt-2">
  {% if member.website %}<a href="{{ member.website }}" target="_blank"><i class="fa fa-home fa-2x"></i></a> {% endif %}
  {% if member.email %}<a href="mailto:{{ member.email }}" target="_blank"><i class="fa fa-envelope-square fa-2x"></i></a> {% endif %}
  {% if member.scholar %}<a href="{{ member.scholar }}" target="_blank"><i class="ai ai-google-scholar-square ai-2x"></i></a> {% endif %}
  {% if member.cv %}<a href="{{ member.cv }}" target="_blank"><i class="ai ai-cv-square ai-2x"></i></a> {% endif %}
  {% if member.github %}<a href="{{ member.github }}" target="_blank"><i class="fa fa-github-square fa-2x"></i></a> {% endif %}
  {% if member.linkedin %}<a href="{{ member.linkedin }}" target="_blank"><i class="fa fa-linkedin-square fa-2x"></i></a> {% endif %}
</div>

  <ul style="overflow: hidden">
  </ul>
</div>

{% assign number_printed = number_printed | plus: 1 %}

{% if even_odd == 1 %}

</div>

{% endif %}

{% endfor %}


{% assign even_odd = number_printed | modulo: 2 %}

{% if even_odd == 1 %}


</div>
{% endif %}

</div>

## Former visitors, BSc/ MSc students

<div style="display: flex; justify-content: space-between; gap: 40px;">

<div style="flex: 1;">
<strong>Visitors</strong>
<ul>
{% for person in site.data.former_ms_bs_student.visitors %}
  <li>{{ person.name }}, {{ person.season }}</li>
{% endfor %}
</ul>
</div>

<div style="flex: 1;">
<strong>Master students</strong>
<ul>
{% for person in site.data.former_ms_bs_student.master_students %}
  <li>{{ person.name }}, {{ person.season }}</li>
{% endfor %}
</ul>
</div>

<div style="flex: 1;">
<strong>Bachelor Students</strong>
<ul>
{% for person in site.data.former_ms_bs_student.bachelor_students %}
  <li>{{ person.name }}, {{ person.season }}</li>
{% endfor %}
</ul>
</div>

</div>

[//]: # (## Administrative Support)

[//]: # ()
[//]: # (<a href="exampleemail@gmail.com">Example staff</a> is helping us &#40;and other groups&#41; with administration.)
