FROM php:8.1-apache

WORKDIR /var/www/html

RUN apt update -y && \
  apt install -y unzip libpq-dev git vim && \
  pecl install xdebug && \
  docker-php-ext-enable xdebug && \
  docker-php-ext-install pgsql pdo_pgsql opcache && \
  a2enmod rewrite && \
  curl -sL https://deb.nodesource.com/setup_current.x | bash - && \
  apt install -y nodejs

COPY --from=composer /usr/bin/composer /usr/bin/composer
