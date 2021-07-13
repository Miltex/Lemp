FROM php:7.4-fpm

RUN apt-get update && \
    apt-get install -y \
        zlib1g-dev && \
    apt-get install -y \
        libpng-dev  && \
    apt-get install -y \
        libzip-dev  

RUN pecl install xdebug \
    && docker-php-ext-enable xdebug
RUN docker-php-ext-install mysqli
RUN docker-php-ext-install gd
RUN docker-php-ext-install zip

COPY --from=composer /usr/bin/composer /usr/bin/composer