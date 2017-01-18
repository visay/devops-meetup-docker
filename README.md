## Docker Images

Searching for images https://hub.docker.com/explore/

- Database: https://hub.docker.com/_/mariadb/ - version: latest
- Wordpress: https://hub.docker.com/_/wordpress/ - version: latest
- TYPO3: https://hub.docker.com/r/martinhelmich/typo3/ - version: latest
- Nginx: https://hub.docker.com/_/nginx/ - version: 1.7

Use `dockerui` + command line to pull and list.

## Dockerfile

Instruction for building docker images.

## Environment variables

## Starting container from image

DB:

```bash
docker run --name db -e MYSQL_DATABASE=wordpress -e MYSQL_ROOT_PASSWORD=root mariadb
```
Wordpress:

```bash
docker run --name wordpress --link db -p 80:80 -e WORDPRESS_DB_HOST=db -e WORDPRESS_DB_NAME=wordpress -e WORDPRESS_DB_PASSWORD=root -e WORDPRESS_DB_USER=root wordpress
```

Access with http://192.168.33.10/

TYPO3:

```bash
docker run --name typo3 --link db -p 8080:80 martinhelmich/typo3
```

Access with http://192.168.33.10:8080/

Neos DB:

```bash
docker run --name neos-db -e MARIADB_PASS=root million12/mariadb
```

Neos:

```bash
docker run --name=neos -p=8081:80 --link neos-db:db -e T3APP_VHOST_NAMES=neos million12/typo3-neos
```

Access with http://192.168.33.10:8081/ and Neos backend login:

- user: admin
- password: password

## Docker compose

- Wordpress: `docker-compose -f wordpress.yml up -d`
- TYPO3: `docker-compose -f typo3.yml up -d`
- Neos: `docker-compose -f neos.yml up -d`

## Docker cloud services

Manually created to build up apps

## Docker cloud stack file

Similar to docker-compose format but not all the same.

## Links:

- Docker cloud: https://cloud.docker.com/
- AWS Console login: https://console.aws.amazon.com/console/home
- Link AWS to docker cloud: https://docs.docker.com/docker-cloud/infrastructure/link-aws/
