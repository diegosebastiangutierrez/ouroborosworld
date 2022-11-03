# OUROBOROS WORLD

create a new repository on the command line

git init  
git add README.md  
git add .gitignore  
git commit -m "Comienzo el primer commit"  
git branch -M main  
git remote add origin git@github.com:diegosebastiangutierrez/ouroborosworld.git  
git push -u origin main  

…or push an existing repository from the command line

git remote add origin git@github.com:diegosebastiangutierrez/ouroborosworld.git  
git branch -M main  
git push -u origin main  

…or import code from another repository

You can initialize this repository with code from a Subversion, Mercurial, or TFS project.

# Docker-based Drupal stack for Ouroboros World Website

[![Build Status](https://github.com/wodby/docker4drupal/workflows/Run%20tests/badge.svg)](https://github.com/wodby/docker4drupal/actions)

## Introduction

Docker4Drupal is a set of docker images optimized for Drupal. Use `docker-compose.yml` file from the [latest stable release](https://github.com/wodby/docker4drupal/releases) to spin up local environment on Linux, Mac OS X and Windows.

* Read the docs on [**how to use**](https://wodby.com/docs/stacks/drupal/local#usage)
* Ask questions on [Slack](http://slack.wodby.com/)
* Follow [@wodbycloud](https://twitter.com/wodbycloud) for future announcements

## Stack

The Drupal stack i use consist of the following containers:

| Container       | Versions                | Image                              | ARM64 support | Enabled by default |
|-----------------|-------------------------|------------------------------------|---------------|--------------------|
| [Nginx]         | 1.21, 1.20, 1.19        | [wodby/nginx]                      | ✓             | ✓                  |
| [Drupal]        | 9, 8, 7                 | [wodby/drupal]                     | ✓             | ✓                  |
| [PHP]           | 8.1, 8.0, 7.4           | [wodby/drupal-php]                 | ✓             |                    |
| Crond           |                         | [wodby/drupal-php]                 | ✓             | ✓                  |
| [MariaDB]       | 10.6, 10.5, 10.4, 10.3  | [wodby/mariadb]                    | ✓             | ✓                  |
| [Mailhog]       | latest                  | [mailhog/mailhog]                  |               | ✓                  |
| phpMyAdmin      | latest                  | [phpmyadmin/phpmyadmin]            |               |                    |
| Traefik         | latest                  | [_/traefik]                        | ✓             | ✓                  |

Supported Drupal versions: 9 / 8 / 7

## Documentation

Full documentation is available at https://wodby.com/docs/stacks/drupal/local.

## Image's tags

Images tags format is `[VERSION]-[STABILITY_TAG]` where:

`[VERSION]` is the _version of an application_ (without patch version) running in a container, e.g. `wodby/nginx:1.15-x.x.x` where Nginx version is `1.15` and `x.x.x` is a stability tag. For some images we include both major and minor version like PHP `7.2`, for others we include only major like Redis `5`.

`[STABILITY_TAG]` is the _version of an image_ that corresponds to a git tag of the image repository, e.g. `wodby/mariadb:10.2-3.3.8` has MariaDB `10.2` and stability tag [`3.3.8`](https://github.com/wodby/mariadb/releases/tag/3.3.8). New stability tags include patch updates for applications and image's fixes/improvements (new env vars, orchestration actions fixes, etc). Stability tag changes described in the corresponding a git tag description. Stability tags follow [semantic versioning](https://semver.org/).

We highly encourage to use images only with stability tags.

## Maintenance

We regularly update images used in this stack and release them together, see [releases page](https://github.com/wodby/docker4drupal/releases) for full changelog and update instructions. Most of routine updates for images and this project performed by [the bot](https://github.com/wodbot) via scripts located at [wodby/images](https://github.com/wodby/images).

## Beyond local environment

Docker4Drupal is a project designed to help you spin up local environment with docker-compose. If you want to deploy a consistent stack with orchestrations to your own server, check out [Drupal stack](https://wodby.com/stacks/drupal) on Wodby ![](https://www.google.com/s2/favicons?domain=wodby.com).

## License

This project is licensed under the MIT open source license.

[Drupal]: https://wodby.com/docs/stacks/drupal/containers#php
[Mailhog]: https://wodby.com/docs/stacks/drupal/containers#mailhog
[MariaDB]: https://wodby.com/docs/stacks/drupal/containers#mariadb
[Nginx]: https://wodby.com/docs/stacks/drupal/containers#nginx
[PHP]: https://wodby.com/docs/stacks/drupal/containers#php
[_/traefik]: https://hub.docker.com/_/traefik
[mailhog/mailhog]: https://hub.docker.com/r/mailhog/mailhog
[phpmyadmin/phpmyadmin]: https://hub.docker.com/r/phpmyadmin/phpmyadmin
[wodby/drupal-php]: https://github.com/wodby/drupal-php
[wodby/drupal]: https://github.com/wodby/drupal
[wodby/mariadb]: https://github.com/wodby/mariadb
[wodby/nginx]: https://github.com/wodby/nginx
