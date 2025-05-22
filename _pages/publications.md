---
title: "Publications"
layout: default
permalink: /publications/
---

<style>
table.pubtable {
  width: 100%;
  border-collapse: collapse;
  margin-top: 2rem;
  font-size: 15px;
}
table.pubtable th, table.pubtable td {
  padding: 10px;
  vertical-align: top;
}
table.pubtable thead {
  font-weight: bold;
  font-size: 16px;
  color: #222;
}
.pubtable .pub-links a {
  color: #e91e63;
  margin-right: 8px;
  text-decoration: none;
  font-weight: 500;
}
.pubtable .pub-links a:hover {
  text-decoration: underline;
}
</style>

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
    {% bibliography --template bib_row %}
  </tbody>
</table>

