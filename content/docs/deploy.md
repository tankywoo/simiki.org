---
layout: page
title: "Deploy"
date: 2014-05-20 08:30
---

## Github Pages ##

[Github Pages](https://pages.github.com/) is the simplest way to deploy your site.

Read the [Github Pages Documents](https://help.github.com/articles/user-organization-and-project-pages) for more detail.

### User Pages ###

Create `User Pages`.

1. Create a repository named `<username>.github.io`. `<username>` is your Github's username.

2. Into your local site, setup a master branch in output directory:

        cd output
        git init
        git add .
        git commit -m 'your comment'
        # These steps will be shown when you create a repo in Github:
        git remote add origin https://github.com/<username>/<username>.github.io.git
        git push -u origin master

3. Back to the parent directory, and touch a `.gitignore` file:

        cd ../
        touch .gitignore

4. Edit `.gitignore` with the contents:

        *.pyc
        output

5. Setup a source branch:

        git init
        git checkout -b source
        git add .
        git commit -m 'your comment'
        # These steps will be shown when you create a repo in Github:
        git remote add origin https://github.com/<username>/<username>.github.io.git
        git push -u origin source

Wait for a while and visit `http://<username>.github.io/`.

### Project Pages ###

#### With Custom Domain ####

1. Create a repository with any name `<projectname>`.

2. Into your local site, setup a master branch in output directory:

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

3. Back to the parent directory, and touch a `.gitignore` file:

        cd ../
        touch .gitignore

4. Edit `.gitignore` with the contents:

        *.pyc
        output

5. Setup a source branch:

        git init
        git add .
        git commit -m 'your comment'
        # These steps will be shown when you create a repo in Github:
        git remote add origin git@github.com:<username>/<projectname>.git
        git push -u origin master

Wait for a while and visit `http://<yourdomain.com>`

Note:

* **Do not** change `url` settings in `_config.yml`.
* If you set project page with domain, visit your wiki with setted domain, not github domain.

More Reference:

* [Adding a CNAME file to your repository](https://help.github.com/articles/adding-a-cname-file-to-your-repository)
* [Tips for configuring a CNAME record with your DNS provider](https://help.github.com/articles/tips-for-configuring-a-cname-record-with-your-dns-provider)

An example:

* [tankywoo/simiki-project-page-with-domain](https://github.com/tankywoo/simiki-project-page-with-domain)
* [http://simiki-project-page-with-domain.simiki.org](http://simiki-project-page-with-domain.simiki.org)

#### Without Custom Domain ####

The project pages url is `http://<username>.github.io/<projectname>`, so you should set `url` to your projectname in `_config.yml`:

    url: <projectname>

The others are the same as `Project Pages with Custom Doamin` above.

## Self-Managed Server ##

Use `scp` or `rsync` to transfer all files in `output` directory to the appropriate web root directory for your web server.

Simiki also support [Fabric](http://www.fabfile.org/) to transfer files. Configure `fabfile.py` and use `fab deploy` to deploy.

## FTP ##

Upload all files in `output` directory by ftp tool to your server.
