FROM barnixcart/workspace:5.3

LABEL maintainer="Pavel Gavrilenko <paulgavrilenko@gmail.com>"

RUN . ~/.bashrc

RUN sed -i "s~{{http_host}}~$APP_DOMAIN~g" /home/xcdocker/.xdev/config.yaml

ARG APP_CODE_PATH_CONTAINER
 
WORKDIR ${APP_CODE_PATH_CONTAINER}
