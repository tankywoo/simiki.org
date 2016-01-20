---
title: "Variables"
date: 2013-10-12 00:00
---

## Site Variables ##

`site` variable is a dict, stored global site configuration and information.

**In addition to the variables list below, some other variables are given in [Configuration](/docs/configuration.html)**

<table class="table table-bordered table-hover" markdown="1">
  <thead>
    <tr>
      <th>Variable</th>
      <th>Description</th>
      <th>Other</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>`site.time`</td>
      <td>The last date time site update/generate</td>
      <td></td>
    </tr>
    <tr>
      <td>`site.structure`</td>
      <td>Store the meta data for all pages. Only exists when generating index. ***This variable will be moved to `pages` variable in the later version***</td>
      <td></td>
    </tr>
    <tr>
      <td>`site.version`</td>
      <td>The version number of Simiki Generator</td>
      <td>New in version 1.5.0</td>
    </tr>
  </tbody>
</table>

## Page Variables ##

`page` variable is a dict, stored the wiki page's meta data and content, etc.

**In addition to the variables list below, some other variables are given in [Meta Data](/docs/metadata.html)**

<table class="table table-bordered table-hover" markdown="1">
  <thead>
    <tr>
      <th>Variable</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>`page.filename`</td>
      <td>Filename of the wiki page. The last pathname component, without slash</td>
    </tr>
    <tr>
      <td>`page.content`</td>
      <td>The body content of html page, without header and footer information</td>
    </tr>
    <tr>
      <td>`page.category`</td>
      <td>The classification category name, relate path to content directory</td>
    </tr>
  </tbody>
</table>

For example, a source file `content/linux/bash.md`, the page.filename is bash.md, the page.category is linux.

## Index Variables ##

`pages` variable is a dict.

***Exists in later version***
