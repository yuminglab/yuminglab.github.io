---
title: "Publications"
layout: htmlpage
permalink: /publications/
---

<style>
h1.page-title {
  color: white;
  margin-top: 20px;
}
h3.pub-section {
  color: #f8f9fa;
  margin-top: 3rem;
  margin-bottom: 1rem;
}
table.pubtable {
  width: 100%;
  border-collapse: collapse;
  font-size: 15px;
  margin-bottom: 2rem;
}
table.pubtable th, table.pubtable td {
  padding: 10px;
  vertical-align: top;
}
table.pubtable thead {
  font-weight: bold;
  font-size: 16px;
  color: white;
  background-color: rgba(26, 188, 156, 0.15);  /* ← 淡绿色背景 */
}

.pubtable .pub-links a {
  color: #e91e63;
  margin: 0 2px;
  text-decoration: none;
  font-weight: 500;
}

.pubtable .pub-links a:hover {
  text-decoration: underline;
}

.pub-links {
  white-space: nowrap; /* 避免自动换行 */
}

ol.bibliography, ul.bibliography {
  display: none !important;
}

li::marker {
  content: "" !important;
}

li {
  list-style: none !important;
  margin: 0;
  padding: 0;
}

.pub-section.preprints {
  color: #1abc9c;
}



.pub-section-wrapper {
  background-color: rgba(255, 255, 255, 0.03);
  padding: 2px;
  border-radius: 12px;
  margin-top: 5px;
  box-shadow: 0 0 15px rgba(0,0,0,0.15);
}



</style>
<div class="pub-section-wrapper">
<h3 class="pub-section preprints">Preprints</h3>

<table class="pubtable">
  <thead>
    <tr>
      <th>Year</th>
      <th>Authors</th>
      <th>Title</th>
      <th>Publication</th>
      <th>Links</th>
    </tr>
  </thead>
  <tbody>
    {% bibliography --query @unpublished --template bib_row %}
  </tbody>
</table>

---
<h3 class="pub-section preprints">Refereed Journal Articles</h3>

<table class="pubtable">
  <thead>
    <tr>
      <th>Year</th>
      <th>Authors</th>
      <th>Title</th>
      <th>Publication</th>
      <th>Links</th>
    </tr>
  </thead>
  <tbody>
    {% bibliography --query @article --template bib_row %}
  </tbody>
</table>

---
<h3 class="pub-section preprints">Refereed Conference Proceedings</h3>

<table class="pubtable">
  <thead>
    <tr>
      <th>Year</th>
      <th>Authors</th>
      <th>Title</th>
      <th>Publication</th>
      <th>Links</th>
    </tr>
  </thead>
  <tbody>
    {% bibliography --query @inproceedings --template bib_row %}
  </tbody>
</table>
</div>





