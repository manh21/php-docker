FROM php:7.3-fpm

MAINTAINER Naufal Hakim <mail@naufalhakim.my.id>

# Get repository and install wget and vim
RUN apt-get update && apt-get install --no-install-recommends -y \
        wget \
        vim \
        git \
        unzip

# Install PHP extensions
ADD https://github.com/mlocati/docker-php-extension-installer/releases/latest/download/install-php-extensions /usr/local/bin/

RUN chmod +x /usr/local/bin/install-php-extensions && \
    install-php-extensions gd redis memcached sqlsrv pdo_sqlsrv opcache apcu apcu_bc iconv mbstring intl mcrypt pgsql mysql mysqli pdo_pgsql pdo_mysql pdo_dblib soap sockets zip pcntl ftp exif gearman

# Clean repository
RUN apt-get clean \
    && rm -rf /var/lib/apt/lists/*

# Fix Sessions Path
RUN echo "session.save_path=\"/tmp\"" >> /usr/local/etc/php/php.ini-development && echo "session.save_path=\"/tmp\"" >> /usr/local/etc/php/php.ini-production

# Volume e área de trabalho
VOLUME ["/var/www/html"]
WORKDIR /var/www/html
EXPOSE 9000