---
title: "基本用法"
date: 2013-10-12 00:00
---

## 基本命令 ##

安装好Simiki后, 就可以使用`simiki`命令.

	# 查看 simiki 命令帮助文档
	$ simiki -h

	# 生成静态页面到output目录 (需要在站点根目录下执行)
	$ simiki g

	# 本地预览模式(开发模式)
	$ simiki p
	
	# 本地预览模式指定绑定IP和端口, 如绑定到所有IP的8888端口
	$ simiki p --host 0.0.0.0 --port 8888
	
	# 本地预览模式监控content目录, 有变更自动更新生成相应静态页面
	$ simiki p -w

监控content目录的预览模式是基于[watchdog](https://github.com/gorakhargosh/watchdog)实现, 对不同系统的参数和内核有一定的限制和要求, 具体见[watchdog文档](https://pythonhosted.org/watchdog/installation.html)

## 扩展命令 ##

Simiki使用 [Fabric](http://www.fabfile.org/) 作为扩展命令工具, 基于Python, 主要提供一些远程部署和本地操作的额外命令.

使用前需要保证已经安装了Fabric, 如果没有可以使用`pip`安装:

	$ pip install fabric

wiki站点初始化时本地已经生成`fabfile.py`.

一些步骤需要`_config.yml`的配置支持, 具体见[部署](/zh-docs/deploy.html)

	# 查看支持的子命令
	$ fab -l
	Available commands:

		commit  Git commit source changes with all tracked/untracked files
		deploy  Deploy your site, support rsync / ftp / github pages

	# 如果wiki站点使用git维护, 则可以使用commit子命令快速提交修改
	$ fab commit

	# 首先配置好_config.yml的deploy配置
	$ fab deploy

	# 如果配置多个deploy项, 可以只指定执行某一种
	$ fab deploy:type=rsync
