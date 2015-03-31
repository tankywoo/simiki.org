---
layout: page
title: "Meta Data"
date: 2014-05-14 00:15
---

Each page use YAML format metadata like:

	---
	layout: page
	title: "Meta Data"
	date: 2014-05-14 00:15
	---

Predefined metadata:

<table class="table table-bordered table-hover" markdown="1">
  <thead>
    <tr>
      <th>Meta</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
  <tr>
    <td>`layout`</td>
    <td>Specify the layout, the file name of theme. Default is `page`</td>
  </tr>
  <tr>
    <td>`title`</td>
    <td>The title of current page `*`</td>
  </tr>
  <tr>
    <td>`date`</td>
    <td>The date time of page creation `*`</td>
  </tr>
  </tbody>
</table>

(`*` stands for `must exist`)
