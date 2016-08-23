FROM php:5.6-fpm

# Configure
COPY ./magerun /usr/local/bin/magerun
COPY ./php-fpm.conf /usr/local/etc/
COPY ./php_production.ini /usr/local/etc/php/php.ini
ENV INSTALLER_VERSION 1.0.0

# Configure PHP
RUN buildDeps=" \
        libpng12-dev \
        libjpeg-dev \
        libmcrypt-dev \
        libxml2-dev \
        freetype* \
    "; \
    set -x \
    && apt-get update && apt-get install -y $buildDeps --no-install-recommends && rm -rf /var/lib/apt/lists/* \
    && docker-php-ext-configure \
    gd --with-png-dir=/usr --with-jpeg-dir=/usr --with-freetype-dir \
    && docker-php-ext-install \
    gd \
    mbstring \
    mysqli \
    mcrypt \
    soap \
    mysql \
    pdo_mysql \
    zip \
    &&  apt-get update && apt-get install -y \
    vim \
    telnet \
    netcat \
    git-core \
    zip \
    mysql-client \
    && chmod +x /usr/local/bin/magerun \
    && apt-get purge -y --auto-remove