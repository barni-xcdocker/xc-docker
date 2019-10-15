ARG APP_PHP_VERSION

FROM barnixcart/php-fpm:xc5-${APP_PHP_VERSION}

ARG APP_PHP_VERSION
ARG SOFTWARE_ENGINE
COPY ./xdebug.ini /usr/local/etc/php/conf.d/xdebug.ini
COPY ./${SOFTWARE_ENGINE}/php${APP_PHP_VERSION}.ini /usr/local/etc/php/php.ini

RUN rm -rf /var/www/html

RUN usermod -u 1000 www-data