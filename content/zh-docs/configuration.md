---
layout: page
title: "配置"
date: 2014-03-01 17:38
---

配置文件是 `_config.yml`.

**注意: 一般情况下, 只需要配置好初始配置文件中给出的配置项.**

## 配置选项 ##

<table class="table table-bordered table-hover" markdown="1">
  <thead>
    <tr>
      <th>配置选项</th>
      <th>说明</th>
      <th>默认值</th>
    </tr>
  </thead>
  <tbody>
  <tr>
    <td>`url`</td>
    <td>站点域名</td>
    <td>`""`</td>
  </tr>
  <tr>
    <td>`title`</td>
    <td>站点标题. 用于网站的一些元信息</td>
    <td>`""`</td>
  </tr>
  <tr>
    <td>`keywords`</td>
    <td>站点的关键字. 用于网站的一些元信息</td>
    <td>`""`</td>
  </tr>
  <tr>
    <td>`description`</td>
    <td>站点的描述信息. 用于网站的一些元信息</td>
    <td>`""`</td>
  </tr>
  <tr>
    <td>`author`</td>
    <td>站点作者</td>
    <td>`""`</td>
  </tr>
  <tr>
    <td>`root`</td>
    <td>
    站点根目录. 大部分情况下不需要填写, 使用默认值即可.<br />如果站点使用子目录, 如`http://example.com/wiki/`, 则需要设置`url`为`http://example.com/wiki/`, 并且设置`root`为`/wiki/`.<br />通常是在使用[Github Pages - Project](https://pages.github.com/)的情况下才需要配置此选项</td>
    <td>`"/"`</td>
  </tr>
  <tr>
    <td>`source`</td>
    <td>存储源文件(目前暂时只支持Markdown)的目录. ***不建议修改默认值***</td>
    <td>`"content"`</td>
  </tr>
  <tr>
    <td>`destination`</td>
    <td>存储生成的静态文件的目录. ***不建议修改默认值***</td>
    <td>`"output"`</td>
  </tr>
  <tr>
    <td>`attach`</td>
    <td>存储附件文件(如图片,压缩包等)的目录.<br />此目录在生成时会拷贝到output目录, 即`attach/path/to/file`会拷贝到`output/attach/path/to/file`.<br />另外此目录默认没有创建, 如果需要可以手工创建. ***不建议修改默认值***</td>
    <td>`"attach"`</td>
  </tr>
  <tr>
    <td>`themes_dir`</td>
    <td>存储所有主题的目录名. 一个主题一个子目录, 全部存放在此目录下. ***不建议修改默认值***</td>
    <td>`"themes"`</td>
  </tr>
  <tr>
    <td>`theme`</td>
    <td>指定使用的主题名. 主题名即存放在`themes_dir`目录下的主题目录名</td>
    <td>`"simple"`</td>
  </tr>
  <tr>
    <td>`default_ext`</td>
    <td>`simiki new`生成一篇wiki时的默认后缀</td>
    <td>`"md"`</td>
  </tr>
  <tr>
    <td>`pygments`</td>
    <td>设置`true`为开启代码高亮</td>
    <td>`true`</td>
  </tr>
  <tr>
    <td>`debug`</td>
    <td>设置`true`为开启调试模式, 会输出更多更详细的信息</td>
    <td>`false`</td>
  </tr>
  </tbody>
</table>

***以上只列出站点全局的基本配置选项, 其它选项见相应的文档***:

* [部署](/zh-docs/deploy.html)


## 样例 ##

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
