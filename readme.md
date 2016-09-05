# Preface

There are a lot of guides and tutorials on the Web for configuring your development/production environment using LAMP/LEMP/etc stack.

A lot of them are outdated, some of them don’t explain anything (only how to get it work), and only small part is actually up-to-date and useful for me. It’s really difficult to find the best practices and you could get confused pretty easily without knowing fundamentals.

For example, when I wanted to install Nginx as front-end reverse-proxy web server to Apache2 v2.4 using Ubuntu 16.04, I’ve googled some guides and tutorials for doing that. Then I have spent 5 hours figuring out why simple setup didn’t actually work the way I wanted to. The problems I had were pretty tricky to google right:

1. Couldn’t make frontend + backend web server setup to actually process PHP files, instead, it was just showing PHP code
2. HTTP header “REMOTE_ADDR” was showing local proxy IP (Nginx) instead of real client IP

It appeared that solutions to the issues were pretty simple, but figuring and finding them out on the Web was absolutely time-consuming.

1. The problem was solved when I’ve disabled default sites-available config from Nginx, used “right” Nginx settings to pass proxy server and figured out what is the difference using sockets vs ports in php-fpm.
2. First, I’ve found a tutorial where you should install and use a module for Apache2 called “mod_rpaf”. It didn’t work no matter what I’ve tried. After even more googling I’ve found that it is actually deprecated, and Apache have built-in “mod_remoteip” that does everything for you out of the box.

Then, I’ve decided to go further and collect everything I’ve learned so far related to web development and explain why you should use or learn the particular topic, not only web servers but also tooling, workflow, code standards, etc. This is an attempt to organize knowledge and experience in a readable way.

I know, it is pretty impossible to cover everything in a single document. I don’t think it’s possible to maintain the huge amount of explanations and keep them up-to-date with modern web either. The purpose of the document is to maintain a list of useful resources and links that explain the tricky parts for the topics and to give developers some kind of starting point, where they could improve their knowledge, stay relevant and grow their vision. Or it could be used to actually learn everything from top to bottom and become more informed about web development… Whatever.

The Internet is a large scrapyard with tiny bits of useful information and I’m trying to separate trash from diamonds. Any comments and pull requests are welcome.

# Table of Contents
1. [HTTP](#http)
   1. [HTTP 1.0](#http-10)
   2. [HTTP 1.1](#http-11)
   3. [HTTP/2](#http2)
2. [nginx](#nginx)
   1. [Basic configuration](#basic-configuration)
   2. [Frontend Reverse Proxy](#frontend-reverse-proxy)
   3. [SSL configuration](#ssl-configuration)
   4. [Pros](#pros)
   5. [Cons](#cons)
3. [Apache2](#apache2)
   1. [Basic configuration](#basic-configuration-1)
   2. [SSL configuration](#ssl-configuration-1)
   3. [Pros](#pros-1)
   4. [Cons](#cons-1)
4. [Let's Encrypt](#lets-encrypt)
   1. [Apache](#apache-1)
   2. [nginx](#nginx-1)
5. [PHP](#php)
   1. [mod_php](#mod_php)
   2. [php-fpm](#php-fpm)
6. [Provisioning and deploying](#provisioning-and-deploying)
   1. [Vagrant](#vagrant)
   2. [PuPHPet](#puphpet)
7. [Git](#git)
   1. [Git Workflow](#git-workflow)
8. [Managing Your Time](#managing-your-time)
   1. [Working remotely](#working-remotely)
   2. [Evidence Based Scheduling](#evidence-based-scheduling)
9. [Writing a better code](#writing-a-better-code)
   1. [The Joel Test](#the-joel-test)
   2. [Painless Bug Tracking](#painless-bug-tracking)

## HTTP

### HTTP 1.0

### HTTP 1.1

### HTTP/2

## nginx

### Basic configuration

### Frontend Reverse Proxy

### SSL configuration

### Pros

### Cons

## Apache2

### Basic configuration

### SSL configuration

### Pros

### Cons

## Let's Encrypt

### Apache

### nginx

## PHP

### mod_php

### php-fpm

## Provisioning and deploying

### Vagrant

### PuPHPet

## Git

### Git Workflow

## Managing Your Time

### Working Remotely

### Evidence Based Scheduling

## Writing a better code

### The Joel Test

### Painless Bug Tracking

## Links used

1. [Differences and dis/advanages between: Fast-CGI, CGI, Mod-PHP, SuPHP, PHP-FPM](http://serverfault.com/questions/645755/differences-and-dis-advanages-between-fast-cgi-cgi-mod-php-suphp-php-fpm)
2. [High load architecture](http://thehighload.com/post/High+load+architecture)
3. [Stop using PHP-FPM to argue using Nginx vs Apache](https://dracony.org/stop-using-php-fpm-to-argue-using-nginx-vs-apache/)
4. [Introduction to Vagrant/Puppet and introducing PuPHPet - A simple to use Vagrant/Puppet GUI Configurator! ](https://jtreminio.com/2013/05/introduction_to_vagrant_puppet_and_introducing_puphpet_a_simple_to_use_vagrant_puppet_gui_configurator/)
5. [Mozilla SSL Configuration Generator](https://mozilla.github.io/server-side-tls/ssl-config-generator/)
6. [Strong Ciphers for Apache, nginx and Lighttpd](https://cipherli.st/)
7. [The Joel Test: 12 Steps to Better Code](http://www.joelonsoftware.com/articles/fog0000000043.html)
8. [Painless Bug Tracking](http://www.joelonsoftware.com/articles/fog0000000029.html)
9. [Evidence Based Scheduling](http://www.joelonsoftware.com/items/2007/10/26.html)