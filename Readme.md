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


##### Add your healtcheck

In this image there's the cgi-fcgi library so easy to test if php-fpm is sane

`cgi-fcgi -bind -connect 127.0.0.1:9000`

##### Why?

Is better to have a sub-image in order to speedup the building process among different projects.
