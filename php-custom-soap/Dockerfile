FROM circleci/php:7.2-node-browsers

RUN sudo apt-get update && \
    sudo apt-get install -y \
    libmcrypt-dev \
    libsqlite3-dev \
    libfreetype6-dev \
    libjpeg62-turbo-dev \
    libpng-dev \
    zlib1g-dev libxml2-dev && \
    sudo docker-php-ext-configure gd --with-jpeg-dir=/usr/include/ && \
    sudo docker-php-ext-install -j$(nproc) iconv gd zip pdo_mysql pdo_sqlite soap && \
    sudo rm /usr/local/etc/php/conf.d/docker-php-ext-xdebug.ini && \
    sudo pecl install mcrypt-1.0.1 && \
    sudo docker-php-ext-enable mcrypt

RUN sudo composer self-update
