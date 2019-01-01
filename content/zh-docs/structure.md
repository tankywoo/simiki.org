---
title: "目录结构"
date: 2013-10-12 00:00
---

使用Simiki初始新建(`simiki init`)后的目录结构如下:

	.
	├── _config.yml
	├── content
	├── fabfile.py
	├── output
	└── themes
		└── simple2

文件/目录说明:

<table class="table table-bordered table-hover" markdown="1">
  <thead>
    <tr>
      <th>文件/目录</th>
      <th>说明</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>`_config.yml`</td>
      <td>站点配置文件. 详细介绍见 [配置](/zh-docs/configuration.html)</td>
    </tr>
    <tr>
      <td>`fabfile.py`</td>
      <td>扩展脚本, 提供一些方便的额外操作. 需要安装[Fabric](http://www.fabfile.org/).<br />其它见[基本用法](/zh-docs/usage.html)和[部署](/zh-docs/deploy.html)</td>
    </tr>
    <tr>
      <td>`content`</td>
      <td>存储源文件(目前暂时只支持Markdown)的目录.<br />**源文件以子目录名分类存放.**<br />如`content/linux/bash.md`表示bash.md这个源文件属于linux分类.<br />**注意**: Simiki 暂时只支持二级目录分类</td>
    </tr>
    <tr>
      <td>`output`</td>
      <td>输出的静态文件(html)目录.<br />***注意: 此目录的生成/更新过程中会存在删除的操作, 请不要将无关且重要的文件放在此目录下***</td>
    </tr>
    <tr>
      <td>`themes`</td>
      <td>存储所有主题的目录. 一个主题一个子目录, 全部存放在此目录下.<br />`_config.yml`配置当前使用的主题</td>
    </tr>
  </tbody>
</table>
