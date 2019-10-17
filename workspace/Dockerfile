FROM phusion/baseimage:latest

LABEL maintainer="Pavel Gavrilenko <paulgavrilenko@gmail.com>"

RUN DEBIAN_FRONTEND=noninteractive
RUN locale-gen en_US.UTF-8

ENV LANGUAGE=en_US.UTF-8
ENV LC_ALL=en_US.UTF-8
ENV LC_CTYPE=en_US.UTF-8
ENV LANG=en_US.UTF-8
ENV TERM xterm

# Add the "PHP 7" ppa
RUN apt-get install -y software-properties-common && \
    add-apt-repository -y ppa:ondrej/php

#
#--------------------------------------------------------------------------
# Software's Installation
#--------------------------------------------------------------------------
#

# Install "PHP Extentions", "libraries", "Software's"
RUN apt-get update && \
    apt-get upgrade -y --option=Dpkg::Options::="--force-confold" && \
    apt-get install -y --allow-downgrades --allow-remove-essential \
        --allow-change-held-packages \
        php7.2-cli \
        php7.2-common \
        php7.2-curl \
        php7.2-json \
        php7.2-xml \
        php7.2-mbstring \
        php7.2-mysql \
        php7.2-zip \
        php7.2-memcached \
        php7.2-gd \
        php7.2-dev \
        pkg-config \
        libcurl4-openssl-dev \
        libedit-dev \
        libssl-dev \
        libxml2-dev \
        git \
        curl \
        vim \
        nano \
    && apt-get clean

# MySQL Client:
RUN apt-get update -yqq && \
  apt-get -y install mysql-client

RUN apt-get update -yqq && \
  apt-get -y install iputils-ping

COPY mysql.cnf /etc/mysql/conf.d/mysql.cnf

ARG MYSQL_HOST
ARG MYSQL_ROOT_USER
ARG MYSQL_ROOT_PASSWORD

RUN sed -i "s~{{MYSQL_HOST}}~$MYSQL_HOST~g" /etc/mysql/conf.d/mysql.cnf \
 && sed -i "s~{{MYSQL_ROOT_USER}}~$MYSQL_ROOT_USER~g" /etc/mysql/conf.d/mysql.cnf \ 
 && sed -i "s~{{MYSQL_ROOT_PASSWORD}}~$MYSQL_ROOT_PASSWORD~g" /etc/mysql/conf.d/mysql.cnf
 
ARG APP_CODE_PATH_CONTAINER
 
WORKDIR ${APP_CODE_PATH_CONTAINER}
