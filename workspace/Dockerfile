FROM barnixcart/workspace:xc5.3

LABEL maintainer="Pavel Gavrilenko <paulgavrilenko@gmail.com>"

ARG XDEV_DEV_MODE

RUN if [ ${XDEV_DEV_MODE} = true ]; then \
    mv /home/xcdocker/xdev /home/xcdocker/~xdev && \
    sed -i "s~/home/xcdocker/xdev/vendor/bin/xdev~/home/xcdocker/xdev/bin/xdev~g" /home/xcdocker/.bash_aliases \
;fi

ARG APP_DOMAIN

RUN sed -i "s~{{http_host}}~$APP_DOMAIN~g" /home/xcdocker/.xdev/config.yaml

ARG APP_CODE_PATH_CONTAINER
WORKDIR ${APP_CODE_PATH_CONTAINER}
