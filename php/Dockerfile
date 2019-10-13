FROM php:7.3-fpm-alpine
# install packages
RUN apk add -U --no-cache \
    bash \
    git \
    curl-dev \
    libxml2-dev \
    postgresql-dev \
    libpng-dev \
    libjpeg-turbo-dev \
    zip \
    libzip-dev \
    unzip \
    gmp-dev
RUN docker-php-ext-install pdo_mysql mysqli mbstring
# install composer
RUN curl -sS https://getcomposer.org/installer | php \
    && mv composer.phar /usr/local/bin/composer

