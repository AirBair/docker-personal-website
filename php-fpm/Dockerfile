FROM php:fpm-alpine

MAINTAINER Florian LE GOFF <contact@florianlegoff.com>

RUN apk update
RUN apk add \
    curl

# intl extension
RUN apk add \
    icu-dev
RUN docker-php-ext-install intl

# Miscellaneous extensions
RUN docker-php-ext-install \
    mysqli \
    pdo_mysql \
    opcache

# Composer
RUN curl -L https://getcomposer.org/composer.phar -o /usr/bin/composer && chmod +x /usr/bin/composer

# PHP-CS-Fixer
RUN curl -L https://cs.symfony.com/download/php-cs-fixer-v2.phar -o /usr/bin/php-cs-fixer && chmod +x /usr/bin/php-cs-fixer

# Remove useless cache files.
RUN rm -rf /var/cache/apk/* && rm -rf /tmp/*

WORKDIR /var/www
