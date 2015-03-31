---
layout: page
title: "Configuration"
date: 2014-03-01 17:38
---

The configuration file is `_config.yml`.

<table class="table table-bordered table-hover" markdown="1">
  <thead>
    <tr>
      <th>Option</th>
      <th>Description</th>
      <th>Default</th>
    </tr>
  </thead>
  <tbody>
  <tr>
    <td>`url`</td>
    <td>Site's url</td>
    <td>`""`</td>
  </tr>
  <tr>
    <td>`title`</td>
    <td>Site's title</td>
    <td>`""`</td>
  </tr>
  <tr>
    <td>`keywords`</td>
    <td>Site's keywords. (default: "")</td>
    <td>`""`</td>
  </tr>
  <tr>
    <td>`description`</td>
    <td>Site's description. (default: "")</td>
    <td>`""`</td>
  </tr>
  <tr>
    <td>`author`</td>
    <td>Site's author</td>
    <td>`""`</td>
  </tr>
  <tr>
    <td>`root`</td>
    <td>Site's root directory, commonly it is '/'. If your site is in a subdirectory, such as `http://example.com/wiki/`, set url as `http://example.com/wiki/` and root as `/wiki/`</td>
    <td>`"/"`</td>
  </tr>
  <tr>
    <td>`source`</td>
    <td>Store the source files, only support markdown file so far</td>
    <td>`"content"`</td>
  </tr>
  <tr>
    <td>`destination`</td>
    <td>Store the output html files</td>
    <td>`"output"`</td>
  </tr>
  <tr>
    <td>`themes_dir`</td>
    <td>The directory to store all the themes</td>
    <td>`"themes"`</td>
  </tr>
  <tr>
    <td>`theme`</td>
    <td>Choose the theme, whose name is the same as directory name under `themes_dir`</td>
    <td>`"simple"`</td>
  </tr>
  <tr>
    <td>`default_ext`</td>
    <td>The default extension when creating a new page</td>
    <td>`"md"`</td>
  </tr>
  <tr>
    <td>`pygments`</td>
    <td>Set true to enable the code lighlight feature</td>
    <td>`true`</td>
  </tr>
  <tr>
    <td>`debug`</td>
    <td>Set true to enable debug mode</td>
    <td>`false`</td>
  </tr>
  </tbody>
</table>


## Example ##

	url: http://simiki.org
	title: Simiki
	keywords: simiki, wiki, python, simple
	description: Simiki is a simple static site generator for wiki.
	author: Tanky Woo

	root: /
	source: content
	destination: output
	themes_dir: themes
	theme: cod

	default_ext: md
	pygments: true
	debug: false
	index: true
