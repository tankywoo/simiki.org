---
title: "Configuration"
date: 2013-10-12 00:00
---

The config file is `_config.yml`.

**Note: In general, you only need to finished configuring the initial config file.**

## Basic Configuration ##

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
      <td>Site url</td>
      <td>`""`</td>
    </tr>
    <tr>
      <td>`title`</td>
      <td>Site title. Used by the meta settings of site</td>
      <td>`""`</td>
    </tr>
    <tr>
      <td>`keywords`</td>
      <td>Site keywords. Used by the meta settings of site</td>
      <td>`""`</td>
    </tr>
    <tr>
      <td>`description`</td>
      <td>Site description. Used by the meta settings of site</td>
      <td>`""`</td>
    </tr>
    <tr>
      <td>`author`</td>
      <td>Site author</td>
      <td>`""`</td>
    </tr>
    <tr>
      <td>`root`</td>
      <td>Site root directory. In general there is no need to set/change this.<br />If your site is in a subdirectory, such as `http://example.com/wiki/`, set url as `http://example.com/wiki/` and root as `/wiki/`.<br />Often set this when using [Github Pages - Project](https://pages.github.com/)</td>
      <td>`"/"`</td>
    </tr>
    <tr>
      <td>`source`</td>
      <td>Directory to store the source files(only support markdown file by now). ***Modify the default value is not recommended***</td>
      <td>`"content"`</td>
    </tr>
    <tr>
      <td>`destination`</td>
      <td>Directory to store the output html files. ***Modify the default value is not recommended***</td>
      <td>`"output"`</td>
    </tr>
    <tr>
      <td>`attach`</td>
      <td>Directory to store the attachment(such as image, compression package, etc.).<br />This directory will be copied to `output/` when do generating, as `attach/path/to/file` will be copied to `output/attach/path/to/file`.<br />This directory doesn't created when init site, if need, you should create it manually. ***Modify the default value is not recommended***</td>
      <td>`"attach"`</td>
    </tr>
    <tr>
      <td>`themes_dir`</td>
      <td>Directory to store all the themes. Every theme is a subdirectory. ***Modify the default value is not recommended***</td>
      <td>`"themes"`</td>
    </tr>
    <tr>
      <td>`theme`</td>
      <td>Specified the theme, whose name is the same as directory name under `themes_dir`</td>
      <td>`"simple"`</td>
    </tr>
    <tr>
      <td>`category`</td>
      <td>Custom settings of category, such as label(alias name), description, etc. Get by the `pages` variable. See the example below</td>
      <td>`None`</td>
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

***Above only list the global site configuration, view other configuration with corresponding documents***:

* [Deploy](/docs/deploy.html)

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

	category:
	  - name: linux  # the category directory name
		label: Linux/运维  # alias name of category, used in index page
	  - name: database
		label: 数据库
	
	default_ext: md
	pygments: true
	debug: false
