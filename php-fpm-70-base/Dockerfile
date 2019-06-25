FROM php:7.0-fpm

ENV INSTALLER_VERSION 1.0.0

RUN buildDeps=" \
libpng-dev \
libjpeg-dev \
libwebp-dev \
libmcrypt-dev \
libxml2-dev \
libfreetype6-dev  \
libfcgi0ldbl \
locales \
"; \
set -x \
&& apt-get update && apt-get install -y $buildDeps --no-install-recommends && rm -rf /var/lib/apt/lists/* \
&& docker-php-ext-configure \
gd --with-png-dir=/usr --with-jpeg-dir=/usr --with-webp-dir=/usr --with-freetype-dir \
&& docker-php-ext-install \
gd \
calendar \
intl \
mbstring  \
mcrypt \
soap \
pdo pdo_mysql \
zip \
&&  apt-get update && apt-get install -y \
vim \
telnet \
netcat \
git-core \
zip \
mysql-client \
&& apt-get purge -y --auto-remove

RUN dpkg-reconfigure locales \
&& locale-gen C.UTF-8 \
&& /usr/sbin/update-locale LANG=C.UTF-8 \
&& tail -n +7 /etc/locale.gen | sed 's/\# //'  > tmp.gen \
&& mv tmp.gen /etc/locale.gen \
&& locale-gen
