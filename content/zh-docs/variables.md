---
title: "变量"
date: 2013-10-12 00:00
---

## 站点变量 ##

`site`变量是一个字典, 存储全局的一些配置和信息.

**除了下面这些, 其它的变量见[配置](/zh-docs/configuration.html)**

<table class="table table-bordered table-hover" markdown="1">
  <thead>
    <tr>
      <th>变量</th>
      <th>说明</th>
      <th>其它</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>`site.time`</td>
      <td>站点最后一次生成更新的时间</td>
      <td></td>
    </tr>
    <tr>
      <td>`site.structure`</td>
      <td>存储所有页面的元信息. 只在生成首页时存在. ***这个变量下一个版本会移到`pages`中***</td>
      <td></td>
    </tr>
    <tr>
      <td>`site.version`</td>
      <td>Simiki的版本号</td>
      <td>1.5.0 版本引入</td>
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
      <td>页面的文件名, 整个路径的最后一部分, 不包含斜线(slash)</td>
    </tr>
    <tr>
      <td>`page.content`</td>
      <td>页面body部分的html内容, 不包括header, footer等信息</td>
    </tr>
    <tr>
      <td>`page.category`</td>
      <td>页面的分类目录名, 相对于content目录的部分</td>
    </tr>
    <tr>
      <td>`page.relation`</td>
      <td>与当前页面相关(同一个tag)的其它文件meta信息列表</td>
    </tr>
  </tbody>
</table>

比如一个源文件`content/linux/bash.md`, page.filename是bash.md, page.category是linux.

## 首页变量 ##

(**1.6版本引入**)

`pages`存储了所有页面的信息, 是一个list变量。

结构如下：

```text
[
  {
    "name": "linux",        # 目录名
    "pages": [
      ...
    ]
  },
  {
    "name": "tool",        # 目录名
    "pages": [             # 目录下的所有页面和集合
      {
        "date": "2016-01-03 00:00",
        "fname": "other1.md",        # 无集合的页面
        ...
      },
      {
        "name": "Version Control",        # 集合名
        "pages": [                        # 集合下的所有页面
          {
            "collection": "Version Control",
            "fname": "git.md",
            "date": "2016-01-01 00:00"
            ...
          },
          {
            "collection": "Version Control",
            "fname": "svn.md",
            "date": "2016-01-02 00:00"
            ...
          }
        ]
      }
    ]
  }
]
```
