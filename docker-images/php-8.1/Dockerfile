FROM php:8.1-fpm

COPY --from=composer:2.2.4 /usr/bin/composer /usr/local/bin/composer

COPY --from=mlocati/php-extension-installer /usr/bin/install-php-extensions /usr/local/bin/

RUN install-php-extensions \
        soap \
        zip \
        bcmath \
        exif \
        gd \
        intl \
        opcache \
        pdo_mysql \
        imagick \
        xdebug \
        pcntl

RUN apt update
RUN apt install -y \
    git \
    nano

COPY image-files /

WORKDIR /var/www
