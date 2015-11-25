---
layout: page
title: "变量"
date: 2014-03-01 17:38
---

## 站点变量 ##

`site`变量是一个字典, 存储全局的一些配置和信息.

**除了下面这些, 其它的变量见[配置](/zh-docs/configuration.html)**

<table class="table table-bordered table-hover" markdown="1">
  <thead>
    <tr>
      <th>变量</th>
      <th>说明</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>`site.time`</td>
      <td>站点最后一次生成更新的时间</td>
    </tr>
    <tr>
      <td>`site.structure`</td>
      <td>存储所有页面的元信息. 只在生成首页时存在. ***这个变量下一个版本会移到`pages`中***</td>
    </tr>
  </tbody>
</table>

## 页面变量 ##

`page`变量是一个字典, 存储一篇wiki的相关信息.

**除了下面这些, 其它变量见[元信息](/zh-docs/metadata.html)**

<table class="table table-bordered table-hover" markdown="1">
  <thead>
    <tr>
      <th>变量</th>
      <th>说明</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>`page.filename`</td>
      <td>页面的文件名</td>
    </tr>
    <tr>
      <td>`page.content`</td>
      <td>页面body部分的html内容, 不包括header, footer等信息</td>
    </tr>
    <tr>
      <td>`page.category`</td>
      <td>页面的分类目录名</td>
    </tr>
  </tbody>
</table>

## 首页变量 ##

`pages`变量是一个字典.

***现在还是`site.structure`, 下一个版本改为pages变量.***
