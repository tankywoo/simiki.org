---
title: "Basic Usage"
date: 2013-10-12 00:00
---

## Basic Usage ##

'simiki' command available after installed Simiki.

	# View help documentation
	$ simiki -h

	# Generate html pages to output directory (must under root directory of site)
	$ simiki g

	# Local preview mode (develop mode)
	$ simiki p
	
	# Local preview mode, with bind IP and port, such as bind to every available IP address and port 8888
	$ simiki p --host 0.0.0.0 --port 8888
	
	# Local preview mode, with watch content directory
	# Auto update and generate html pages if there is change
	$ simiki p -w

The content directory watcher is base on [watchdog](https://github.com/gorakhargosh/watchdog), there are some dependencies and caveats with different platforms, more details are given in [watchdog installation](https://pythonhosted.org/watchdog/installation.html)

## Extended Tools ##

Simiki use [Fabric](http://www.fabfile.org/) as extended tool, based on Python. The `fabfile.py` provide some management for remote operation.

Make sure you have installed Fabric before using it, with `pip`:

	$ pip install fabric

`fabfile.py` will exists after initialled wiki site.

Some operation need support form `_config.yml`, more details view [Configuration](/docs/deploy.html)

	# View sub-commands
	$ fab -l
	Available commands:

		commit  Git commit source changes with all tracked/untracked files
		deploy  Deploy your site, support rsync / ftp / github pages

	# Use commit sub-command to fast commit changes if wiki site is managed with git.
	$ fab commit

	# Make sure the `deploy` settings in `_config.yml`
	$ fab deploy

	# If configured multiple deploy items, you can only run one specified item
	$ fab deploy:type=rsync
