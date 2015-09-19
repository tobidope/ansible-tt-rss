[![Build Status](https://travis-ci.org/tobidope/ansible-tt-rss.svg?branch=master)](https://travis-ci.org/tobidope/ansible-tt-rss)

tt-rss
======

Installs an instance of Tiny Tiny RSS on a system using PostgreSQL, ready to use.

Requirements
------------

No special requirements

Role Variables
--------------

	# Database user
	ttrss_db_user: ttrss
	# Database password, please change when using the role
	ttrss_db_password: ttrss
	# Database name
	ttrss_db_name: ttrss
	# Database encoding
	ttrss_db_encoding: "UTF-8"
	# Databse collation, defines sort order and character classification
	ttrss_db_collate: "de_DE.UTF-8"
	# Database ctype, defines character classification
	ttrss_db_ctype: "de_DE.UTF-8"
	# URL of the Tiny Tiny RSS git repository, change when you want to use a fork
	ttrss_git_repo: "https://tt-rss.org/gitlab/fox/tt-rss.git"
	# Path to the folder, where Tiny Tiny RSS will be installed
	ttrss_install_path: "/var/www/rss"
	#  URL PATH of the Tiny Tiny RSS installation, change only when you know what you do
	ttrss_url_path: "{{ ttrss_install_path | basename }}"
	# Enable gzip out to improve wire performance, This requires PHP Zlib extension on the server
	# Set to True or False
	ttrss_enable_gzip: true
	# Sets log destination for Tiny Tiny RSS
	# syslog - logs to system log
	# sql - logs to database, can be seen in Preferences -> System
	# '' - uses PHP logging, usually the http server error log
	ttrss_log_destination: syslog

Dependencies
------------

No dependencies

Example Playbook
----------------

    - hosts: servers
      roles:
         - { role: tt-rss, ttrss_db_password: secret }

License
-------

GPL-V3

Author Information
------------------

Created by Tobias Bell

* [GitHub](https://github.com/tobidope)
* [Twitter](https://twitter.com/tobidope)

