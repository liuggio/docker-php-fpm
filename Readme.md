docker- php-fpm
==============

This is my standard base image for php-fpm,
is the standard Docker image that extends the standard php-fpm.

##### Contains

- gd
- mbstring
- mysqli
- mcrypt
- mysql client
- pdo_mysql
- zip
- git-core
- composer

##### Why?

Is better to have a sub-image in order to speedup the building process among different projects.