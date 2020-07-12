FROM php:8.0-rc-apache

RUN apt-get update \
    && apt-get install -y zip unzip vim libpq-dev \
    && docker-php-ext-install pdo_mysql pdo_pgsql

RUN apt-get install -y libjpeg-dev libpng-dev libfreetype6-dev
RUN docker-php-ext-configure gd --with-freetype=/usr/include/ --with-jpeg=/usr/include/ \
        && docker-php-ext-install -j$(nproc) gd
COPY httpd.conf /etc/apache2/sites-available/httpd.conf
RUN a2dissite httpd.conf && a2ensite httpd.conf && a2enmod rewrite

