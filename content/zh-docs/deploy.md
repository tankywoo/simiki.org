---
title: "部署"
date: 2013-10-12 00:00
---

部署与生成的 `output` 目录内容相关。

下面介绍几种常用的部署模式，支持使用基本的命令工具，或者基于我们写好的 [fabfile.py](/zh-docs/usage.html#\_2)。

## 自己的服务器 ##

通过 `rsync` 或者 `scp` 命令，将 `output` 目录的静态文件传到自己服务器的相应站点根目录，配合 [Web Server](https://en.wikipedia.org/wiki/Web_server)（如 Nginx, Apache 等）。

如果使用 Fabric，则需要在 `_config.yml` 中配置 `deploy` 配置项：

	deploy:
	  - type: rsync
		user: <login username>
		host: <remote host ip or domain>
		dir: <path to store files/dirs under output>

这个会将 output 目录下的子文件 / 子目录，基于 SSH 的 Rsync 方式，传输到远程主机的配置的 dir 目录下。

如果不想每次部署都输入密码，则可以配置 [SSH Private/Public Key](https://www.digitalocean.com/community/tutorials/how-to-set-up-ssh-keys--2)

执行部署命令：

	$ fab deploy


## 虚拟主机 (FTP) ##

通过 `sftp` 或 `ftp` 命令将 `output` 传到虚拟主机下的目录，通过空间商提供的后台做好相应的配置。

如果使用 Fabric，则需要在 `_config.yml` 中配置 `deploy` 配置项：

	deploy:
	  - type: ftp
		host: <remote host ip or domain>
		port: <remote host port, default is 21>
		user: <login username>
		password: <login password>
		dir: <path to store files/dirs under output>

这个会将 output 目录下的子文件 / 子目录，基于 FTP 方式，传输到远程主机的配置的 dir 目录下。

**注意**: 如果配置了 password，不要把此配置提交 Git 甚至推送到 Github 等公共仓库！

**建议**: 配置 password 并且将值留空，则每次执行部署时会提供输入密码：

	deploy:
	  - type: ftp
		host: 1.1.1.1
		user: bob
		password:         # 建议这里留空，每次输入密码
		dir: /

执行部署命令：

	$ fab deploy


## Github Pages ##

[Github Pages](https://pages.github.com/) 可以让你不需要购买服务器、虚拟主机，即可拥有自己的站点。

如果使用 Fabric，则需要在 `_config.yml` 中配置 `deploy` 配置项：

	deploy:
	  - type: git
		remote: <remote repo name, default is 'origin'>
		branch: <branch, default is 'gh-pages'>

这个会将 output 目录下的子文件 / 子目录，基于 Git 方式，推送到远程仓库相应的分支。

**注意**:

* 首先确保本地已经和远程仓库关联，即执行 `git remote -v` 可以看到远程仓库的 url
* 需要先安装 [ghp-import](https://github.com/davisp/ghp-import)，一个基于 Python 的工具。讨论见 [issue 23](https://github.com/tankywoo/simiki/issues/23)

执行部署命令：

	$ fab deploy


---

下面的步骤是最原始(后续可能弃用)的方式, 比较麻烦. 可以不必阅读.

更详细的可以阅读 [Github Pages 文档](https://help.github.com/articles/user-organization-and-project-pages)。

### User Pages ###

创建 `User Pages`。

1. 创建一个仓库，仓库名 `<username>.github.io`。 其中 `<username>` 是 Github 的用户名。

2. 在 wiki 的 output 目录下，git 初始化，创建默认的 `master` 分支：

		cd output
		git init
		git add .
		git commit -m 'your comment'
		# 以下步骤会在 Github 上创建一个空项目后提示
		git remote add origin https://github.com/<username>/<username>.github.io.git
		git push -u origin master

3. 回到上层目录，创建 `.gitignore` 文件：

		cd ../
		echo -e '*.pyc\noutput' > .gitignore

4. 创建 `source` 分支：

		git init
		git checkout -b source
		git add .
		git commit -m 'your comment'
		# 以下步骤会在 Github 上创建一个空项目后提示
		git remote add origin https://github.com/<username>/<username>.github.io.git
		git push -u origin source

最后稍等几分钟，然后访问 `http://<username>.github.io/`。

绑定域名的方式可以参考下面的 Project Pages。

### Project Pages ###

Project Pages 分两种：

* 绑定自定义域名
* 不绑定域名

#### 绑定自定义域名 ####

1. 创建一个仓库，仓库名 `<projectname>`。

2. 在 wiki 的 output 目录下，git 初始化，创建 `gh-pages` 分支：

		cd output
		git init
		git checkout -b gh-pages
		git add .
		git commit -m 'your comment'
		# 以下步骤会在 Github 上创建一个空项目后提示
		git remote add origin git@github.com:<username>/<projectname>.git
		git push -u origin gh-pages

3. 回到上层目录，创建 `.gitignore` 文件：

		cd ../
		echo -e '*.pyc\noutput' > .gitignore

4. 创建 `master` 分支：

		git init

		# 将要绑定的域名写到站点根目录下的 CNAME 文件中
		echo "<yourdomain.com>" > CNAME

		git add .
		git commit -m 'your comment'
		# 以下步骤会在 Github 上创建一个空项目后提示
		git remote add origin git@github.com:<username>/<projectname>.git
		git push -u origin master

最后稍等几分钟，然后访问 `http://<yourdomain.com>`。

***注意***：

* **不要** 修改 `_config.yml` 中的 `root` 配置项。
* 如果绑定了域名，请使用相应域名访问 wiki，而不要用 Github 提供的二级域名，否则会导致一些静态文件加载错误。

更多参考：

* [Adding a CNAME file to your repository](https://help.github.com/articles/adding-a-cname-file-to-your-repository)
* [Tips for configuring a CNAME record with your DNS provider](https://help.github.com/articles/tips-for-configuring-a-cname-record-with-your-dns-provider)

以下是配置好的样例：

* [tankywoo/simiki-project-page-with-domain](https://github.com/tankywoo/simiki-project-page-with-domain)
* [http://simiki-project-page-with-domain.simiki.org](http://simiki-project-page-with-domain.simiki.org)

#### 不绑定域名 ####

如果不绑定域名，则 Github 会提供一个带有子目录的二级域名：`http://<username>.github.io/<projectname>`。

所以需要相应设置 `_config.yml` 中的 `root` 配置项：

	root: /<projectname>

其它都和上面的 **Project Pages with Custom Doamin** 一样。

以下是配置好的样例：

* [tankywoo/simiki-project-page-without-domain](https://github.com/tankywoo/simiki-project-page-without-domain)
* [http://tankywoo.github.io/simiki-project-page-without-domain/](http://tankywoo.github.io/simiki-project-page-without-domain/)
