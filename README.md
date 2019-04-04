# redmine settings by docker-compose
redmine, postgres, nginx ssl settings by docker-compose

## Prerequisites
* certbot cli for nginx
* docker, docker-compose
* specific docker version of posgres, redmine, nginx

## Setup
1. get ssl certificates by certbot cli
```bash
certbot certonly --standalone -d mydomain.com
```
2. docker-compose up
```bash
docker-compose up -d
```
3. Add redmine plugins, themes for your own
- if plugins : follow the plugins tutorials
```bash
docker exec -it compose_redmine_image  /bin/bash
bundle install
rake redmine:plugins:migrate RAILS_ENV=production
```
- if themes : just clone the project into themes dir

## TODO
- [ ] certbot-auto update issue
- [ ] certbot crontab in docker-compose
- [ ] improve security f nginx config
- [ ] email setup
