FROM httpd:2.4
 
ARG WEB_USER
ARG WEB_GROUP
ARG APACHE_ROOT_DIR
ARG APP_DOMAIN
ARG APP_WEB_ROOT_DIR

COPY httpd.conf ${APACHE_ROOT_DIR}/conf/httpd.conf
COPY httpd-vhosts.conf ${APACHE_ROOT_DIR}/conf/extra/httpd-vhosts.conf
COPY ssl ${APACHE_ROOT_DIR}/ssl/

RUN sed -i "s~{{ServerName}}~$APP_DOMAIN~g" ${APACHE_ROOT_DIR}/conf/extra/httpd-vhosts.conf \
 && sed -i "s~{{DocumentRoot}}~$APP_WEB_ROOT_DIR~g" ${APACHE_ROOT_DIR}/conf/extra/httpd-vhosts.conf

#RUN chgrp -R ${WEB_GROUP} ${APACHE_ROOT_DIR}/conf/httpd.conf \
# && chgrp -R ${WEB_GROUP} ${APACHE_ROOT_DIR}/conf/extra/httpd-vhosts.conf
 
RUN usermod -u 1000 ${WEB_USER} \
 && groupmod -g 1000 ${WEB_GROUP} \
 && chgrp -R ${WEB_GROUP} ${APACHE_ROOT_DIR}