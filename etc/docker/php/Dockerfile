FROM php:7.4.6-fpm

COPY ./php.ini /usr/local/etc/php/php.ini

RUN apt-get update \
    && apt-get install -y git iputils-ping nano acl openssl openssh-client wget zip vim libssh-dev \
    libpng-dev zlib1g-dev libzip-dev libxml2-dev libicu-dev
#    && docker-php-ext-install intl pdo pdo_mysql zip gd soap bcmath sockets
#    && pecl install xdebug \
#    && docker-php-ext-enable --ini-name 05-opcache.ini opcache xdebug
#RUN apt-get update && apt-get install -y \
#    git zip unzip

RUN curl https://getcomposer.org/composer.phar -o /usr/bin/composer && chmod +x /usr/bin/composer
RUN composer self-update

#RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer --version=1.10.16
#RUN composer --version

RUN mkdir -p /app/www

WORKDIR /app/www