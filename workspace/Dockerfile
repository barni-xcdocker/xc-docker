ARG TAG_WORKSPACE
FROM barnixcart/workspace:${TAG_WORKSPACE}

LABEL maintainer="Pavel Gavrilenko <paulgavrilenko@gmail.com>"

# Uncomment if you need to customize php.ini
#COPY ./php/php.ini /etc/php/7.x/cli/php.ini

ARG APP_CODE_PATH_CONTAINER
WORKDIR ${APP_CODE_PATH_CONTAINER}
