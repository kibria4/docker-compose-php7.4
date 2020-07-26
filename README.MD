# Docker Compose - Nginx, PHP 7.4-fpm, Postgres

A full docker compose setup for your PHP project for local development. Originally set up to work for Symfony 4+ projects, but can be tweaked to work in any PHP project. Thanks to https://github.com/ineat/docker-php-nginx-postgres-composer for pointing me in the right direction. I made some slight tweaks to use PHP 7.4-fpm easily and using Postgres for database.

## Prerequisites
* Docker v1.13.0+
* Docker Compose (should come with Docker)

## Installing Docker
* Windows 10 Home: https://docs.docker.com/docker-for-windows/install-windows-home/
* Windows 10 Pro: https://docs.docker.com/docker-for-windows/install/
* Mac (2010 model or newer): https://docs.docker.com/docker-for-mac/install/
* Ubuntu: https://docs.docker.com/engine/install/ubuntu/
* Other Linux flavour: Simply search for install docker on ~Linux distro~ and should find helpful articles

## Quick Guide:
* Clone this into your project root folder
* Go to .docker/nginx/default.conf and update the root folder AFTER /var/www/html (the public folder to access in browser, i.e. for Symfony it is "public", so /var/www/html/public)
* Go to .docker/php/php.ini and add configuration specific to your project needs
* Go to .docker/Dockerfile and on the same line as "install-php-extensions ...", add the extensions you need (list of available extensions here: https://github.com/mlocati/docker-php-extension-installer). You can also change the PHP version at the top. I set default to latest stable FPM. Currently only tested with PHP FPM.
* Go to docker-compose.yaml and check all required services are enabled. I have added PG Admin, Redis, RabbitMQ and Mailcatcher but commented out. Uncomment if you want to use this
* In terminal, "cd" to project root, and then run: docker-compose up -d
* In your browser, go to localhost

## TODO for this project
* Add support for other databases
* Show examples of using this in other popular PHP projects, such as Laravel, WordPress, etc
