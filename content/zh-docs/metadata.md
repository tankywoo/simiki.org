---
title: "页面头信息"
date: 2013-10-12 00:00
---

wiki页面的元数据使用的是YAML Front Matter格式:

	---
	title: "页面头信息"
	date: 2013-10-12 00:00
	---

预定义的元数据字段:

<table class="table table-bordered table-hover" markdown="1">
  <thead>
    <tr>
      <th>元数据字段</th>
      <th>说明</th>
      <th>其它</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>`title`</td>
      <td>一篇wiki的标题</td>
      <td>**必填**</td>
    </tr>
    <tr>
      <td>`date`</td>
      <td>一篇wiki创建的时间, 格式是`YYYY-mm-dd HH:MM`</td>
      <td>**必填**</td>
    </tr>
    <tr>
      <td>`updated`</td>
      <td>一篇wiki的最后修改时间, 格式是`YYYY-mm-dd HH:MM`</td>
      <td>可选</td>
    </tr>
    <tr>
      <td>`layout`</td>
      <td>指定页面使用的布局格式, 和主题的相应模版名一致</td>
      <td>默认是`page`</td>
    </tr>
    <tr>
      <td>`collection`</td>
      <td>页面的集合。详细见[集合/标签](/zh-docs/collection_and_tag.html)。</td>
      <td>可选</td>
    </tr>
    <tr>
      <td>`tag`</td>
      <td>页面的标签，以`逗号`分隔的字符串或者是列表。详细见[集合/标签](/zh-docs/collection_and_tag.html)。</td>
      <td>可选</td>
    </tr>
    <tr>
      <td>`draft`</td>
      <td>布尔变量, 设置`true`表示此页面是草稿, 不会生成静态页面</td>
      <td>默认是`false`</td>
    </tr>
    <tr>
      <td>`render`</td>
      <td>布尔变量, 设置`false`表示此页面不做markup解析, 原生输出</td>
      <td>默认是`false`</td>
    </tr>
  </tbody>
</table>
