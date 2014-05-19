---
layout: page
title: "Directory Structure"
date: 2014-05-14 00:00
---

An initial Simiki site looks like this:

	.
	├── _config.yml
	├── content
	├── fabfile.py
	├── output
	└── themes
		└── simple

<table class="table table-bordered table-hover" markdown="1">
<thead>
<tr>
<th>File/Directory</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>`_config.yml`</td>
<td>Configuration file. see [Configuration](/docs/configuration.html).</td>
</tr>
<tr>
<td>`content`</td>
<td>Store the source files(`.md` files) by category. For example, `bash.md` file belonging to `linux` classification, the path should be `content/linux/bash.md` as a second-level structure. **NOTE**: Simiki only support top-level and second-level so far.</td>
</tr>
<tr>
<td>`output`</td>
<td>The html files generated by Simiki. Suggest to add this directory in `.gitignore`</td>
</tr>
<tr>
<td>`themes`</td>
<td>Put themes in this directory, each theme is a subdirectory. Configure the theme in `_config.yml`.</td>
</tr>
</tbody>
</table>