---
layout: page
title: "Deploy"
date: 2014-05-20 08:30
---

## Deploy with Github Pages ##

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


## Deploy with your host ##

TODO
