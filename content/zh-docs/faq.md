---
title: "常见问题"
date: 2013-10-12 00:00
---

### Windows下使用Simiki ###

Simiki对Windows的支持不是很好, 如果可能, 请尽量选择在 `Unix` / `Linux` / `Mac` 下使用.

如果使用[Fabric](http://www.fabfile.org/index.html), 可能会出现一些问题, 首先确认安装了以下模块:

[`pycrypto`](http://www.voidspace.org.uk/python/modules.shtml#pycrypto):

	easy_install http://www.voidspace.org.uk/downloads/pycrypto26/pycrypto-2.6.win32-py2.7.exe

[`ecdsa`](https://pypi.python.org/pypi/ecdsa/):

	pip install ecdsa

参考:

* [Fabric installs but doesn’t run!](http://www.fabfile.org/faq.html#fabric-installs-but-doesn-t-run)
* [Fabric 1.8.4 and 1.9.0 don't work on OS X 10.9](https://github.com/fabric/fabric/issues/1157)
* [simiki issue #34](https://github.com/tankywoo/simiki/issues/34)

### 自定义首页 ###

Simiki默认会自动生成首页.

如果想自定义首页, 可以在`source`目录下创建`index.md`, Simiki会生成相应的自定义首页.

### 对TOC的支持吗? ###

是的, 支持 TOC (Table Of Content). 在YAML Front Matter下面, wiki内容的顶部，添加一行即可:

	---
	title: "Hello World"
	date: 2015-01-01 00:00
	---

	[TOC]

	<your content>

### Feed ###

***注意***:

1. 暂时只支持Atom, 不支持RSS2.0
2. 此功能处于测试阶段, 后续可能会有较大的改动

将`atom.xml`放在wiki目录下:

```xml
<?xml version="1.0" encoding="utf-8"?>
{% if site.url %}
  {% set site_url = "%s%s"|format(site.url, site.root) %}
{% else %}
  {% set site_url = site.url %}
{% endif %}
<feed xmlns="http://www.w3.org/2005/Atom">
  <generator uri="http://simiki.org/" version="{{ site.version }}">Simiki</generator>
  <title>{{ site.title }}</title>
  <link href="{{ site_url }}/" />
  <link href="{{ site_url }}/atom.xml" rel="self" type="application/atom+xml" />
  <updated>{{ site.time|rfc3339 }}</updated>
  <id>{{ site_url }}</id>
  <author>
    <name>{{ site.author|e }}</name>
  </author>
  {% for f, page in pages.iteritems() %}
    {% set uri = site_url ~ f|replace('content/', '/', 1)|replace('.md', '.html', 1) %}
  <entry>
    <id>{{ uri }}</id>
    <title>{{ page.title|e }}</title>
    <link href="{{ uri }}" />
    <published>{{ page.date|rfc3339 }}</published>

    {% if page.updated %}
    <updated>{{ page.updated|rfc3339 }}</updated>
    {% else %}
    <updated>{{ page.date|rfc3339 }}</updated>
    {% endif %}

    {% if page.category %}
    <category term="{{ page.category }}" />
    {% endif %}

    {% if page.content %}
    <content type="html">{{ page.content|e }}</content>
    {% endif %}
    {% if page.summary %}
    <summary>{{ page.summary|e }}</summary>
    {% endif %}
  </entry>
  {% endfor %}
</feed>
```

主题的`base.html`的`<head>`与`</head>`之间添加一行:

```html
<link rel="alternate" type="application/atom+xml" href="atom.xml" title="Atom feed">
```

### Favicon ###

(v1.5.0.post1版本)

将文件名为`favicon.ico`的icon文件放在wiki根目录下.

另外, 主题需要额外支持:

	<link rel="shortcut icon" href="{{ site.root }}/favicon.ico" type="image/x-icon">
	<link rel="icon" href="{{ site.root }}/favicon.ico" type="image/x-icon">
