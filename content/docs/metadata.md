---
title: "Meta Data"
date: 2013-10-12 00:00
---

Each page use YAML format metadata like:

	---
	title: "Meta Data"
	date: 2013-10-12 00:00
	---

Predefined meta data:

<table class="table table-bordered table-hover" markdown="1">
  <thead>
    <tr>
      <th>Meta</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>`title`</td>
      <td>The title of current wiki page (**Required**)</td>
    </tr>
    <tr>
      <td>`date`</td>
      <td>The date time of wiki page creation, with format `YYYY-mm-dd HH:MM` (**Required**)</td>
    </tr>
    <tr>
      <td>`updated`</td>
      <td>The last modified date time of wiki page, with format `YYYY-mm-dd HH:MM`</td>
    </tr>
    <tr>
      <td>`layout`</td>
      <td>Specify the layout template to use, the same name with template under used theme. Default is `page`</td>
    </tr>
    <tr>
      <td>`draft`</td>
      <td>Boolean value, if this page is draft and do not want to generate html page, set `true`. Default is `false`</td>
    </tr>
    <tr>
      <td>`render`</td>
      <td>Boolean value, if do not want to parse this page with markup, set `false`. Default is `true`</td>
    </tr>
  </tbody>
</table>
