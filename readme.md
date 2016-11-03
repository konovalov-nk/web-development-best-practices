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
   4. [HTTP Caching](#http-caching)
2. [Nginx](#nginx)
   1. [Basic configuration](#basic-configuration)
   2. [Frontend Reverse Proxy](#frontend-reverse-proxy)
   3. [SSL configuration](#ssl-configuration)
   4. [Thread Pools in Nginx](#thread-pools-in-nginx)
   5. [Pros](#pros)
   6. [Cons](#cons)
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
6. [Ruby](#ruby)
   1. [RVM](#rvm)
7. [Frameworks](#frameworks)
   1. [Laravel](#laravel)
   2. [Ruby on Rails](#ruby-on-rails)
8. [Provisioning and Deploying](#provisioning-and-deploying)
   1. [Vagrant](#vagrant)
   2. [PuPHPet](#puphpet)
9. [Git](#git)
   1. [Git Workflow](#git-workflow)
10. [Relational Databases](#relational-databases)
   1. [MySQL](#mysql)
   2. [PostgreSQL](#postgresql)
   3. [Database Indexing](#database-indexing)
   4. [Query Optimisation](#query-optimisation)
   5. [Sargable statements](#sargable-statements)
11. [Managing Your Time](#managing-your-time)
   1. [Working remotely](#working-remotely)
   2. [Evidence Based Scheduling](#evidence-based-scheduling)
   3. [Why are software development estimates regularly off by a factor of 2-3 times?](#why-are-software-development-estimates-regularly-off-by-a-factor-of-2-3-times)
   4. [Programmer Interrupted](#programmer-interrupted)
   5. [Working asynchronously](#working-asynchronously)
12. [Writing a Better Code](#writing-a-better-code)
   1. [The Joel Test](#the-joel-test)
   2. [Painless Bug Tracking](#painless-bug-tracking)
   3. [Unit Testing](#unit-testing)
   4. [Behavior Testing](#behavior-testing)
   5. [What technical details should a programmer of a web application consider before making the site public?](#what-technical-details-should-a-programmer-of-a-web-application-consider-before-making-the-site-public)
13. [Security Concerns](#security-concerns)
   1. [The definitive guide to form-based website authentication](#the-definitive-guide-to-form-based-website-authentication)
   2. [How to do stateless and cookie-less authentication?](how-to-do-stateless-and-cookie-less-authentication)

## HTTP

### HTTP 1.0

### HTTP 1.1

### HTTP/2

### HTTP Caching

## nginx

### Basic configuration

### Frontend Reverse Proxy

### SSL configuration

### Thread Pools in Nginx

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

## Ruby

### RVM

## Frameworks

### Laravel

### Ruby on Rails

## Provisioning and deploying

### Vagrant

### PuPHPet

## Git

### Git Workflow

## Relational Databases

### MySQL

### PostgreSQL

### Database Indexing

### Query Optimisation

### Sargable statements

## Managing Your Time

### Working Remotely

### Evidence Based Scheduling

### Why are software development estimates regularly off by a factor of 2-3 times?

### Programmer Interrupted

### Working asynchronously

## Writing a better code

### The Joel Test

### Painless Bug Tracking

### Unit Testing

### Behavior Testing

### What technical details should a programmer of a web application consider before making the site public?

## Security Concerns

### The definitive guide to form-based website authentication

### How to do stateless and cookie-less authentication?

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
10. [What technical details should a programmer of a web application consider before making the site public?](http://programmers.stackexchange.com/questions/46716/what-technical-details-should-a-programmer-of-a-web-application-consider-before)
11. [Why are software development estimates regularly off by a factor of 2-3 times?](http://www.michaelrwolfe.com/2013/10/19/50/)
12. [Programmer Interrupted](http://blog.ninlabs.com/2013/01/programmer-interrupted/)
13. [Working asynchronously](http://blog.vivekhaldar.com/post/26291176846/working-asynchronously)
14. [Sargability: Why %string% Is Slow](https://www.brentozar.com/archive/2010/06/sargable-why-string-is-slow/)
15. [How does database indexing work?](http://stackoverflow.com/questions/1108/how-does-database-indexing-work)
16. [Sargable conditions in Relational Databases](https://en.wikipedia.org/wiki/Sargable)
17. [The definitive guide to form-based website authentication](http://stackoverflow.com/a/477578/2959158)
18. [How to do stateless (session-less) & cookie-less authentication?](http://stackoverflow.com/questions/20588467/how-to-do-stateless-session-less-cookie-less-authentication)
19. [Things Caches Do](http://2ndscale.com/rtomayko/2008/things-caches-do)
20. [HTTP Caching](http://www.peej.co.uk/articles/http-caching.html)
21. [Thread Pools in NGINX Boost Performance 9x!](https://www.nginx.com/blog/thread-pools-boost-performance-9x/)