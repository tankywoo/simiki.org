---
layout: page
title: "Deploy"
date: 2014-05-20 08:30
---

## Github Pages ##

[Github Pages](https://pages.github.com/) is the simplest way to deploy your site.

Read the [Github Pages Documents](https://help.github.com/articles/user-organization-and-project-pages) and create `User Pages`.

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


## Self-managed server ##

Use `scp` or `rsync` to transfer all files in `output` directory to the appropriate web root directory for your web server.

Simiki also support [Fabric](http://www.fabfile.org/) to transfer files. Configure `fabfile.py` and use `fab deploy` to deploy.

## FTP ##

Upload all files in `output` directory by ftp tool to your server.
