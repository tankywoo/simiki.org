---
title: "Themes"
date: 2013-10-12 00:00
---

Simiki theme use [Jinja2](http://jinja.pocoo.org/), a full featured template engine, based on Python.

A simplest theme only need `index.html` and `page.html`:

* `index.html` is used for index page as catalog
* `page.html` is used for every wiki page.

Default theme named `simple2` will exists after initialled wiki site.

More themes in [simiki-themes](https://github.com/tankywoo/simiki-themes).

If you have create a new theme, welcome to give me a Pull Request by [Git Submodule](https://git-scm.com/docs/git-submodule).

## Filter ##

In addition to Jinja [builtin filters](http://jinja.pocoo.org/docs/dev/templates/#list-of-builtin-filters), We have provided some custom filters:

<table class="table table-bordered table-hover" markdown="1">
  <thead>
    <tr>
      <th>Filter</th>
      <th>Description</th>
      <th>Other</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>`rfc3339`</td>
      <td>Convert `datetime.datetime` object to [RFC3339](https://www.ietf.org/rfc/rfc3339.txt) format string</td>
      <td>New in version 1.5.0</td>
    </tr>
  </tbody>
</table>
