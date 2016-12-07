FROM php:7-fpm-alpine

RUN apk add --update --no-cache libintl icu icu-dev libxml2-dev postgresql-dev \
    && docker-php-ext-install intl zip soap pdo_mysql pdo_pgsql \
    && rm -rf /var/cache/apk/*

RUN apk upgrade --update && apk add msmtp sed curl \
  coreutils \
  freetype-dev \
  libjpeg-turbo-dev \
  libltdl \
  libmcrypt-dev \
  libpng-dev \
&& docker-php-ext-install -j$(nproc) iconv mcrypt \
&& docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ \
&& docker-php-ext-install -j$(nproc) gd intl opcache \
&& rm -rf /var/cache/apk/*

RUN docker-php-source extract \
    && apk add --no-cache --virtual .phpize-deps-configure $PHPIZE_DEPS \
    && pecl install xdebug \
    && docker-php-ext-enable xdebug \
    && apk del .phpize-deps-configure \
    && docker-php-source delete \
    && rm -rf /var/cache/apk/*

COPY php.ini /usr/local/etc/php/