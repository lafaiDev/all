Zend Application 
=======================

Introduction
------------
This is a simple, skeleton application using the ZF2 MVC , doctrine , ajax and module
systems. This application is meant to be used as a starting place for those
looking to get their feet wet with ZF2.

Installation using Composer
---------------------------


### Installation using a tarball with a local Composer and git



Download composer into your project directory and install the dependencies:

          git clone https://github.com/lafaiDev/all.git
        
   if your composer integer in your path windows
   
          $php composer install

If you don't have access to curl, then install Composer into your project as per the [documentation](https://getcomposer.org/doc/00-intro.md).

Web server setup
----------------

### PHP CLI server

The simplest way to get started if you are using PHP 5.4 or above is to start the internal PHP cli-server in the root
directory:

    php -S 0.0.0.0:8080 -t public/ public/index.php

This will start the cli-server on port 8080, and bind it to all network
interfaces.


### data basse doctrine 


	php vendor/doctrine/doctrine-module/bin/doctrine-module.php orm:schema-tool:update --force

**Note:** cree data base name 'all_db' and run cmd*.
### Apache setup

To setup apache, setup a virtual host to point to the public/ directory of the
project and you should be ready to go! It should look something like below:

    <VirtualHost *:80>
        ServerName all.localhost
        DocumentRoot /path/all/public
        <Directory /path/all/public>
            DirectoryIndex index.php
            AllowOverride All
            Order allow,deny
            Allow from all
            <IfModule mod_authz_core.c>
            Require all granted
            </IfModule>
        </Directory>
    </VirtualHost>

