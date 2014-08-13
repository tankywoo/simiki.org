---
layout: page
title: "Configuration"
date: 2014-03-01 17:38
---

## Site ##

The configuration file is `_config.yml`.

<table class="table table-bordered table-hover" markdown="1">
<thead>
<tr>
	<th>Option</th>
	<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>`url`</td>
<td>The url of site</td>
</tr>
<tr>
<td>`title`</td>
<td>The title of site</td>
</tr>
<tr>
<td>`keywords`</td>
<td>The keywords of site</td>
</tr>
<tr>
<td>`description`</td>
<td>The description of site</td>
</tr>
<tr>
<td>`author`</td>
<td>The author of site</td>
</tr>
<tr>
<td>`root`</td>
<td>If your site is in a subdirectory, such as `http://example.com/wiki/`, set url as `http://example.com/wiki/` and root as `/wiki/`</td>
</tr>
<tr>
<td>`source`</td>
<td>Store the source files, only support markdown file so far. Default is `content`, you'd better not to change it unless necessary.</td>
</tr>
<tr>
<td>`destination`</td>
<td>Store the output html files. Default is `output`, you'd better not to change it unless necessary</td>
</tr>
<tr>
	<td>`themes_dir`</td>
	<td>Store all the themes. Default is `themes`, unless necessary, you'd better not to change it.</td>
</tr>
<tr>
	<td>`theme`</td>
	<td>Choose the theme, whose name is the same as directory name under `themes_dir`, such as `theme: simple`</td>
</tr>
<tr>
	<td>`default_ext`</td>
	<td>The default extension when creating a new page, default is `md`</td>
</tr>
<tr>
	<td>`pygments`</td>
	<td>Enable the code lighlight feature, default is enabled.</td>
</tr>
<tr>
	<td>`debug`</td>
	<td>Debug mode, default is disabled.</td>
</tr>
<tr>
	<td>`index`</td>
	<td>Set `true` to use "index.md" under source directory as index page, or set any wiki file, such as "tool/git.md".Default is `false`, Simiki will automatically generate catalog as index page.</td>
</tr>
</tbody>
</table>

## Initial content ##

The content of initial configuration file looks like this:

	url:
	title:
	keywords:
	description:
	author:

All the other configuration items use the default value.

## Example ##

<div class="alert alert-warning alert-block">
<h4>Warning!</h4>
This is only an example, do not simply copy and use it!
</div>

A configuration file example:

	url: http://wiki.tankywoo.com
	title: Wiki · Tanky Woo
	keywords: wiki, makrdown, linux, python, cpp, ops, simiki
	description: "Focus on Python, C/C++, Linux, Ops-Dev, Gentoo, and so on."
	author: Tanky Woo

	root: /
	source: content
	destination: output
	themes_dir: themes
	theme: yasimple

	default_ext: "markdown"
	pygments: true
	debug: false
	index: true
