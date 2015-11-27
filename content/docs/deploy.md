---
title: "Deploy"
date: 2013-10-12 00:00
---

Deployment is related to the content of `content` directory.

Below list some common deployment mode/method, which support basic command tool, or based on [fabfile](/docs/usage.html#\_2)

## Self-Managed Server ##

Use `rsync` or `scp` command, transfer the content of output directory to the root path of your server, configured with [Web Server](https://en.wikipedia.org/wiki/Web_server)(Such as Nginx, Apache, etc.)

If use Fabric, you need to add `deploy` settings in `_config.yml`:

	deploy:
	  - type: rsync
		user: <login username>
		host: <remote host ip or domain>
		dir: <path to store files/dirs under output>

This will transfer the sub-file/sub-directory under output to the remote server, with configured directory path, base on Rsync with SSH.

If you don't want to enter password every time, you can configure [SSH Private/Public Key](https://www.digitalocean.com/community/tutorials/how-to-set-up-ssh-keys--2)

Run deploy command:

	$ fab deploy


## FTP Server ##

Use `sftp` or `ftp` command, upload the content of output directory to the root path of your server, configured from the background of server service provider.

If use Fabric, you need to add `deploy` settings in `_config.yml`:

	deploy:
	  - type: ftp
		host: <remote host ip or domain>
		port: <remote host port, default is 21>
		user: <login username>
		password: <login password>
		dir: <path to store files/dirs under output>

This will upload the sub-file/sub-directory under output to the remote server, with configured directory path, base on FTP.

**NOTE**: If configured password, DO NOT to put this config file to public server, such as Github public repository!

**Advice**: Configure password with empty value, this will let you enter password every time:

	deploy:
	  - type: ftp
		host: 1.1.1.1
		user: bob
		password:         # Leave this value be empty
		dir: /

Run deploy command:

	$ fab deploy


## Github Pages ##

[Github Pages](https://pages.github.com/) helps you build your own site, without to buy VPS/Virtual Host.

If use Fabric, you need to add `deploy` settings in `_config.yml`:

	deploy:
	  - type: git
		remote: <remote repo name, default is 'origin'>
		branch: <branch, default is 'gh-pages'>

This will push the sub-file/sub-directory under output to the remote repository, with configured branch, based on Git.

**NOTE**:

* Make sure you have set remote-tracking reposistory/branch, use `git remote -v` to list the remote reposistory.
* Make sure you have installed [ghp-import](https://github.com/davisp/ghp-import), a github-pages tool base on Python. More details see [issue 23](https://github.com/tankywoo/simiki/issues/23)

Run deploy command:

	$ fab deploy


Below procedures are the origin method, and more trouble. More details are give in [Github Pages Documentation](https://help.github.com/articles/user-organization-and-project-pages/)

### User Pages ###

Create `User Pages`.

1. Create a repository named `<username>.github.io`. `<username>` is your Github's username.

2. Into your local site, setup a `master` branch in output directory:

		cd output
		git init
		git add .
		git commit -m 'your comment'
		# These steps will be shown when you create a repo in Github:
		git remote add origin https://github.com/<username>/<username>.github.io.git
		git push -u origin master

3. Back to the parent directory, and create a `.gitignore` file:

		cd ../
		echo '*.pyc\noutput' > .gitignore

4. Setup a `source` branch:

		git init
		git checkout -b source
		git add .
		git commit -m 'your comment'
		# These steps will be shown when you create a repo in Github:
		git remote add origin https://github.com/<username>/<username>.github.io.git
		git push -u origin source

Wait for a while and visit `http://<username>.github.io/`.

### Project Pages ###

Project Pages have two types:

* With custom domain
* Without custom domain

#### With Custom Domain ####

1. Create a repository with any name `<projectname>`.

2. Into your local site, setup a `gh-pages` branch in output directory:

        cd output
        git init
        git checkout -b gh-pages
        # Write your domain in file named CNAME
        echo "<yourdomain.com>" > CNAME
        git add .
        git commit -m 'your comment'
        # These steps will be shown when you create a repo in Github:
        git remote add origin git@github.com:<username>/<projectname>.git
        git push -u origin gh-pages

3. Back to the parent directory, and create a `.gitignore` file:

		cd ../
		echo '*.pyc\noutput' > .gitignore

4. Setup a `master` branch:

        git init
        git add .
        git commit -m 'your comment'
        # These steps will be shown when you create a repo in Github:
        git remote add origin git@github.com:<username>/<projectname>.git
        git push -u origin master

Wait for a while and visit `http://<yourdomain.com>`

Note:

* **DO NOT** change `root` settings in `_config.yml`.
* If you set project page with domain, visit your wiki with setted domain, not github domain.

More Reference:

* [Adding a CNAME file to your repository](https://help.github.com/articles/adding-a-cname-file-to-your-repository)
* [Tips for configuring a CNAME record with your DNS provider](https://help.github.com/articles/tips-for-configuring-a-cname-record-with-your-dns-provider)

An example:

* [tankywoo/simiki-project-page-with-domain](https://github.com/tankywoo/simiki-project-page-with-domain)
* [http://simiki-project-page-with-domain.simiki.org](http://simiki-project-page-with-domain.simiki.org)

#### Without Custom Domain ####

The project pages url is `http://<username>.github.io/<projectname>`, so you should set `root` to your projectname in `_config.yml`:

    root: /<projectname>

The others are the same as **Project Pages with Custom Doamin** above.

An example:

* [tankywoo/simiki-project-page-without-domain](https://github.com/tankywoo/simiki-project-page-without-domain)
* [http://tankywoo.github.io/simiki-project-page-without-domain/](http://tankywoo.github.io/simiki-project-page-without-domain/)

**NOTE**:

If `root` is setted in `_config.yml`, you should use `--ignore-root` when you want to preview in local environment. And regenerate without `--ignore-root` when you prepare to deploy to remote server.

    simiki generate --ignore-root

