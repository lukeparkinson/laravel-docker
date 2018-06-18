FROM php:7.2-fpm

RUN docker-php-ext-install mysqli pdo pdo_mysql

RUN pecl install -o -f redis \
&&  rm -rf /tmp/pear \
&&  docker-php-ext-enable redis

RUN apt-get update && apt-get install -y \
        git gcc make autoconf libc-dev pkg-config libmcrypt-dev

RUN pecl install -o -f mcrypt-1.0.1

RUN docker-php-ext-enable mcrypt
