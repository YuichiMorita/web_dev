FROM php:7-fpm-alpine

RUN docker-php-ext-install pdo_mysql mysqli mbstring
RUN apk add curl
RUN curl -sS https://getcomposer.org/installer | php
RUN mv composer.phar /usr/local/bin/composer
RUN composer self-update
RUN composer global require hirak/prestissimo

