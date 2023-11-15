# Docker-based Laravel stack

[![Build Status](https://github.com/wodby/docker4laravel/workflows/Run%20tests/badge.svg)](https://github.com/wodby/docker4laravel/actions)

## Introduction

docker4laravel is a set of docker images optimized for Laravel. Use `docker-compose.yml` file from the [latest stable release](https://github.com/wodby/docker4laravel/releases) to spin up local environment on Linux, Mac OS X and Windows. 

* Read the docs on [**how to use**](https://wodby.com/docs/stacks/laravel/local#usage)
* Ask questions on [Discord](http://discord.wodby.com/)
* Ask questions on [Slack](http://slack.wodby.com/)
* Follow [@wodbycloud](https://twitter.com/wodbycloud) for updates announcements

## Stack

The Laravel stack consist of the following containers:

| Container       | Versions                      | Image                              | ARM64 support | Enabled by default |
|-----------------|-------------------------------|------------------------------------|---------------|--------------------|
| [Nginx]         | 1.25, 1.24                    | [wodby/nginx]                      | ✓             | ✓                  |
| [Apache HTTPD]  | 2.4                           | [wodby/apache]                     | ✓             |                    |
| [PHP]           | 8.2, 8.1, 8.0                 | [wodby/laravel-php]                | ✓             | ✓                  |
| Queue           |                               | [wodby/laravel-php]                | ✓             |                    |
| Crond           |                               | [wodby/laravel-php]                | ✓             |                    |
| [MariaDB]       | 11.0, 10.11, 10.6, 10.5, 10.4 | [wodby/mariadb]                    | ✓             | ✓                  |
| [PostgreSQL]    | 16, 15, 14, 13, 12            | [wodby/postgres]                   | ✓             |                    |
| [Redis]         | 7, 6                          | [wodby/redis]                      | ✓             |                    |
| [Memcached]     | 1                             | [wodby/memcached]                  |               |                    |
| [Node.js]       | 20, 18                        | [wodby/node]                       |               |                    |
| [Varnish]       | 6.0                           | [wodby/varnish]                    |               |                    |
| [Solr]          | 8                             | [wodby/solr]                       |               |                    |
| [Elasticsearch] | 7                             | [wodby/elasticsearch]              |               |                    |
| [Kibana]        | 7                             | [wodby/kibana]                     |               |                    |
| [OpenSMTPD]     | 6.0                           | [wodby/opensmtpd]                  |               |                    |
| [Mailhog]       | latest                        | [mailhog/mailhog]                  |               | ✓                  |
| [AthenaPDF]     | 2.16.0                        | [arachnysdocker/athenapdf-service] |               |                    |
| [Rsyslog]       | latest                        | [wodby/rsyslog]                    |               |                    |
| [Webgrind]      | 1                             | [wodby/webgrind]                   |               |                    |
| [Xhprof viewer] | latest                        | [wodby/xhprof]                     |               |                    |
| Adminer         | 4.6                           | [wodby/adminer]                    |               |                    |
| phpMyAdmin      | latest                        | [phpmyadmin/phpmyadmin]            |               |                    |
| Traefik         | latest                        | [_/traefik]                        | ✓             | ✓                  |
                                                                                                 
## Documentation

Full documentation is available at https://wodby.com/docs/stacks/laravel/local

## Images' tags

Images tags format is `[VERSION]-[STABILITY_TAG]` where:

`[VERSION]` is the _version of an application_ (without patch version) running in a container, e.g. `wodby/nginx:1.15-x.x.x` where Nginx version is `1.15` and `x.x.x` is a stability tag. For some images we include both major and minor version like PHP `7.2`, for others we include only major like Redis `5`. 

`[STABILITY_TAG]` is the _version of an image_ that corresponds to a git tag of the image repository, e.g. `wodby/mariadb:10.2-3.3.8` has MariaDB `10.2` and stability tag [`3.3.8`](https://github.com/wodby/mariadb/releases/tag/3.3.8). New stability tags include patch updates for applications and image's fixes/improvements (new env vars, orchestration actions fixes, etc). Stability tag changes described in the corresponding a git tag description. Stability tags follow [semantic versioning](https://semver.org/).

We highly encourage to use images only with stability tags.

## Maintenance

We regularly update images used in this stack and release them together, see [releases page](https://github.com/wodby/docker4laravel/releases) for full changelog and update instructions. Most of routine updates for images and this project performed by [the bot](https://github.com/wodbot) via scripts located at [wodby/images](https://github.com/wodby/images).

## Other Docker4x projects

* [docker4php](https://github.com/wodby/docker4php)
* [docker4drupal](https://github.com/wodby/docker4drupal)
* [docker4wordpress](https://github.com/wodby/docker4wordpress)
* [docker4ruby](https://github.com/wodby/docker4ruby)
* [docker4python](https://github.com/wodby/docker4python)

## License

This project is licensed under the MIT open source license.

[Apache HTTPD]: https://wodby.com/docs/stacks/laravel/containers#apache
[AthenaPDF]: https://wodby.com/docs/stacks/laravel/containers#athenapdf
[Elasticsearch]: https://wodby.com/docs/stacks/elasticsearch
[Kibana]: https://wodby.com/docs/stacks/elasticsearch
[Mailhog]: https://wodby.com/docs/stacks/laravel/containers#mailhog
[MariaDB]: https://wodby.com/docs/stacks/laravel/containers#mariadb
[Memcached]: https://wodby.com/docs/stacks/laravel/containers#memcached
[Nginx]: https://wodby.com/docs/stacks/laravel/containers#nginx
[Node.js]: https://wodby.com/docs/stacks/laravel/containers#nodejs
[OpenSMTPD]: https://wodby.com/docs/stacks/laravel/containers#opensmtpd
[PHP]: https://wodby.com/docs/stacks/laravel/containers#php
[PostgreSQL]: https://wodby.com/docs/stacks/laravel/containers#postgresql
[Redis]: https://wodby.com/docs/stacks/laravel/containers#redis
[Rsyslog]: https://wodby.com/docs/stacks/laravel/containers#rsyslog
[Solr]: https://wodby.com/docs/stacks/solr
[Varnish]: https://wodby.com/docs/stacks/laravel/containers#varnish
[Webgrind]: https://wodby.com/docs/stacks/laravel/containers#webgrind
[XHProf viewer]: https://wodby.com/docs/stacks/laravel/containers#xhprof-viewer

[_/traefik]: https://hub.docker.com/_/traefik
[arachnysdocker/athenapdf-service]: https://hub.docker.com/r/arachnysdocker/athenapdf-service
[mailhog/mailhog]: https://hub.docker.com/r/mailhog/mailhog
[phpmyadmin/phpmyadmin]: https://hub.docker.com/r/phpmyadmin/phpmyadmin
[wodby/adminer]: https://hub.docker.com/r/wodby/adminer
[wodby/apache]: https://github.com/wodby/apache
[wodby/elasticsearch]: https://github.com/wodby/elasticsearch
[wodby/kibana]: https://github.com/wodby/kibana
[wodby/mariadb]: https://github.com/wodby/mariadb
[wodby/memcached]: https://github.com/wodby/memcached
[wodby/nginx]: https://github.com/wodby/nginx
[wodby/node]: https://github.com/wodby/node
[wodby/opensmtpd]: https://github.com/wodby/opensmtpd
[wodby/laravel-php]: https://github.com/wodby/laravel-php
[wodby/postgres]: https://github.com/wodby/postgres
[wodby/redis]: https://github.com/wodby/redis
[wodby/rsyslog]: https://hub.docker.com/r/wodby/rsyslog
[wodby/solr]: https://github.com/wodby/solr
[wodby/varnish]: https://github.com/wodby/varnish
[wodby/webgrind]: https://hub.docker.com/r/wodby/webgrind
[wodby/xhprof]: https://hub.docker.com/r/wodby/xhprof
