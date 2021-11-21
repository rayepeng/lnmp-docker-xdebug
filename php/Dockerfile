######
# See: https://hub.docker.com/_/php/
######

#FROM php:7.0.5-fpm
FROM php:5.6.30-fpm
MAINTAINER prontosil <xinyongp@gmail.com>


RUN mkdir -p /usr/share/nginx/html 
WORKDIR /usr/share/nginx/html
COPY sources.list /etc/apt/sources.list

RUN apt-get update && apt-get install -y \
    libfreetype6-dev \
    libjpeg62-turbo-dev \
    libmcrypt-dev \
    libpng12-dev \
    && docker-php-ext-install -j$(nproc) iconv mcrypt \
    && pecl install xdebug \
    && docker-php-ext-enable xdebug \
    && docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ \
    && docker-php-ext-install -j$(nproc) gd 

RUN docker-php-ext-install -j$(nproc) mysqli
RUN docker-php-ext-install -j$(nproc) zip
RUN docker-php-ext-install -j$(nproc) opcache
RUN docker-php-ext-install -j$(nproc) pdo_mysql
RUN docker-php-ext-install -j$(nproc) bcmath
RUN docker-php-ext-install -j$(nproc) mysql
COPY redis.tar.gz /tmp/
RUN tar xfz /tmp/redis.tar.gz     && rm -r /tmp/redis.tar.gz     && mkdir -p /usr/src/php/ext     && mv redis-4.3.0 /usr/src/php/ext/redis     && docker-php-ext-install redis
