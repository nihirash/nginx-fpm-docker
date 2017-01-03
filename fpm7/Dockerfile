FROM php:7.0-fpm

# ...

RUN apt-get update && apt-get install -y \
    libpq-dev \
    libmemcached-dev \
    curl \
    libmcrypt-dev

# Install PDO/MySQL
RUN docker-php-ext-install pdo pdo_mysql

# Install Memcached for php 7
RUN curl -L -o /tmp/memcached.tar.gz "https://github.com/php-memcached-dev/php-memcached/archive/php7.tar.gz" \
    && mkdir -p /usr/src/php/ext/memcached \
    && tar -C /usr/src/php/ext/memcached -zxvf /tmp/memcached.tar.gz --strip 1 \
    && docker-php-ext-configure memcached \
    && docker-php-ext-install memcached \
    && rm /tmp/memcached.tar.gz

# ...
COPY php.ini /etc/php/7.0/fpm/


CMD ["php-fpm"]


EXPOSE 9000
