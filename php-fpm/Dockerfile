ARG TAG_PHP_FPM

FROM barnixcart/php-fpm:${TAG_PHP_FPM}

COPY ./xdebug.ini /usr/local/etc/php/conf.d/xdebug.ini

# Uncomment if you need to customize php.ini
#COPY ./php/php.ini /usr/local/etc/php/php.ini

RUN usermod -u 1000 www-data

WORKDIR /var/www
