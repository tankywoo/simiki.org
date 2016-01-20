---
title: "主题"
date: 2013-10-12 00:00
---

Simiki 主题使用的[Jinja2](http://jinja.pocoo.org/), 一个强大的模板引擎, 由Python开发.

一个简单的主题只需要包含`index.html`和`page.html`:

* `index.html`: 用于生成站点的首页目录
* `page.html`: 用于生成每一篇wiki

wiki站点初始时在`themes`目录下会有默认的`simple`主题.

更多的主题见 [simiki-themes](https://github.com/tankywoo/simiki-themes).

如果你开发了其它主题, 欢迎以[Git Submodule](https://git-scm.com/docs/git-submodule)的形式给我们的主题仓库提Pull Request.

## 过滤器 ##

除了Jinja[内置的过滤器](http://jinja.pocoo.org/docs/dev/templates/#list-of-builtin-filters), 我们还提供额外的一些自定义过滤器:

<table class="table table-bordered table-hover" markdown="1">
  <thead>
    <tr>
      <th>过滤器</th>
      <th>说明</th>
      <th>其它</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>`rfc3339`</td>
      <td>将`datetime.datetime`对象转换为[RFC3339](https://www.ietf.org/rfc/rfc3339.txt)格式的字符串</td>
      <td>1.5.0 版本引入</td>
    </tr>
  </tbody>
</table>
