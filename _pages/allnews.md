---
title: "News"
layout: gridlay
sitemap: false
permalink: /allnews.html
---
<style>
.pub-section.preprints {
  color: #1abc9c;
}
</style>

<h3 class="pub-section preprints">News</h3>

<div class="col-md-12 col-sm-12">
{% for article in site.data.news %}
<div class="jumbotron" style="padding: 1rem; margin-bottom: 1rem;">
<b>{{ article.date }}</b><br/>
{{ article.headline }}
</div>
{% endfor %}
</div>



