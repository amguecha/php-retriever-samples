### PHP-RETRIEVER AND SAMPLE CONTENT | SIMPLE MVC FRONT CONTROLLER MINI FRAMEWORK

Version: 0.2
License: GPLv3 or later
Requires at least: PHP 7.3+
Contributors: Amaro Guerra Rocha
Source: https://github.com/amguecha/php-retriever-samples
License URI: https://www.gnu.org/licenses/gpl-3.0.en.html


### 0. FILES MANIFEST.

php-retriever-main (entries with * are files added/edited to/in base framework)
|
├── configuration.php 
├── database.php 
├── LICENSE.txt (*) 
├── README.txt (*) 
├── retriever.php 
├── router.php 
|
├── controllers 
│   ├── examples_controller.php (*) 
│   └── home_controller.php 
├── models 
│   ├── examples_model.php (*) 
│   └── home_model.php
├── views 
|   ├── components.php (*) 
|   ├── content.php (*) 
|   ├── cookie.php (*) 
|   ├── database.php (*) 
|   ├── files.php (*) 
|   ├── get.php (*) 
|   ├── icons.php (*) 
|   ├── index.php (*) 
|   ├── page.php (*) 
|   ├── post.php (*) 
|   ├── session.php (*) 
|   └── errors 
|       └── 404.php 
|
└── public_html 
    └── .htaccess 
	├── index.php 
	├── css 
	│   └── bootstrap 
	│       ├── bootstrap-css-5.1.1.css 
	|		├── bootstrap-icons-1.5.0.css 
	│       └── fonts 
	│           ├── bootstrap-icons.woff 
	│           └── bootstrap-icons.woff2     
	├── images 
	│   └── favicon.ico 
	├── js 
	│   └── bootstrap 
	│       └── bootstrap-js-5.1.1.js 
	└── uploads (*) 
	      └── test-image.png (*) 


### 1. INSTALLATION INSTRUCTIONS FOR TESTING IN LOCALHOST.

FOR THE MAIN FRAMEWORK: Unpack the file in your Apache server's directory. Make sure 
the 'public_html' folder is the only one with public access. 

FOR THE SAMPLE CONTENT: Once the framework has been set up, unpack the file inside the 
root directory of the framework itself. Some files will be overwritten, others will be
pasted and will be new.

This framework needs at least an Apache server configured with PHP 7.3+ and Mysql.

Configure the required global constants that are placed in '/configration.php', 
to match your installation, domain, server setup and database credential names.

A Mysql database is required for this framework.

In Linux, you can start Mysql with this log in command:

	mysql -u root -p

Then, create the database and a testing table:

	CREATE DATABASE IF NOT EXISTS php_retriever_main;
	USE php_retriever_main;
	CREATE TABLE IF NOT EXISTS crud (id int NOT NULL, title text NOT NULL, description text NOT NULL) ENGINE=InnoDB DEFAULT CHARSET=utf8;
	ALTER TABLE crud ADD PRIMARY KEY (id);
	ALTER TABLE crud MODIFY id int NOT NULL AUTO_INCREMENT, AUTO_INCREMENT=1;
	COMMIT;


### 2. GENERAL OPERATING INSTRUCTIONS.

This framework uses $_SERVER['REQUEST_URI'] to build up 'paths'
to classes and methods, redirecting the user in that manner.

IMPORTANT: The Front Controller (/public_html/index.php) is in 
charge of passing the path information from a URL (like this one 
'www.domain.com/controller/method') to the router '/router.php', 
which then will point to the corresponding controller file 
and method. No more 'levels' are allowed, just controller->method.

IMPORTANT: Controller files must be named as '*classname*_controller.php'
and must have only one class inside called after the file name 
'*classname*_controller', where *classname* is up to you.

IMPORTANT: model files must be named as '*classname*_model.php'
and must have only one class inside called after the file name 
'*classname*_model', where *classname* is up to you.

The retriever class, inside '/retriever.php' is the one used to 
include, load data and instantiate both models and views inside
methods of each controller. When loading files, the complete name and
extension must be given.

Once all is set up, open your terminal, go to 'public_html' folder, 
and run a PHP server on a free port to start exploring.

In Linux, you can run these commands: 
	
	cd /var/www/html/php-retriever-main/public_html/
	php -S localhost:8080


### 3. LIST OF INCLUDED COMPONENTS.

a) Bootstrap CSS and JS v5.1.1
b) Bootstrap Icons v1.5.0
d) Sample content: (extra files added to base framework)
	d.1) in views:
		bootstrapicons.php
		components.php
		content.php
		cookie.php
		database.php
		files.php
		get.php
		page.php
		post.php
		session.php
	d.2) in models:
		examples_model.php
	d.3) in controllers:
		examples_controller.php
	d.4) in public_html:
		/uploads (and its content)


### 4. LICENSE.

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.

For more information, check LICENCE.txt.

This program bundles the following third-party resources:

	Bootstrap front-end toolkit.
	License: The MIT License (MIT).
	Source: https://github.com/twbs/bootstrap
	Copyright (c) 2011-2021 The Bootstrap Authors, 2011-2021 Twitter, Inc.

	Bootstrap icon library.
	License: The MIT License (MIT).
	Source: https://github.com/twbs/icons
	Copyright (c) 2011-2021 The Bootstrap Authors, 2011-2021 Twitter, Inc.

