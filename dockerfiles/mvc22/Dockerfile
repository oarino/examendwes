FROM php:7.2-apache
# RUN docker-php-ext-install mysqli
RUN docker-php-ext-install pdo pdo_mysql
# /usr/local/bin/docker-php-ext-install -j5 gd mbstring mysqli pdo pdo_mysql shmop

RUN a2dismod rewrite headers


ENV APACHE_DOCUMENT_ROOT=/var/www/html
RUN sed -ri -e 's!/var/www/html!${APACHE_DOCUMENT_ROOT}!g' /etc/apache2/sites-available/*.conf
RUN sed -ri -e 's!/var/www/!${APACHE_DOCUMENT_ROOT}!g' /etc/apache2/apache2.conf /etc/apache2/conf-available/*.conf
