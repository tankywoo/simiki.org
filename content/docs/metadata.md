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
      <th>Other</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>`title`</td>
      <td>The title of current wiki page</td>
      <td>**Required**</td>
    </tr>
    <tr>
      <td>`date`</td>
      <td>The date time of wiki page creation, with format `YYYY-mm-dd HH:MM`</td>
      <td>**Required**</td>
    </tr>
    <tr>
      <td>`updated`</td>
      <td>The last modified date time of wiki page, with format `YYYY-mm-dd HH:MM`</td>
      <td>Optional</td>
    </tr>
    <tr>
      <td>`layout`</td>
      <td>Specify the layout template to use, the same name with template under used theme</td>
      <td>Default is `page`</td>
    </tr>
    <tr>
      <td>`collection`</td>
      <td>The collection of page. More details view [Collection/Tag](/docs/collection_and_tag.html).</td>
      <td>Optional</td>
    </tr>
    <tr>
      <td>`tag`</td>
      <td>The tag of page, comma separated string or list. More details view [Collection/Tag](/docs/collection_and_tag.html).</td>
      <td>Optional</td>
    </tr>
    <tr>
      <td>`draft`</td>
      <td>Boolean value, if this page is draft and do not want to generate html page, set `true`. Default is `false`</td>
      <td>Default is `false`</td>
    </tr>
    <tr>
      <td>`render`</td>
      <td>Boolean value, if do not want to parse this page with markup, set `false`. Default is `true`</td>
      <td>Default is `false`</td>
    </tr>
  </tbody>
</table>
