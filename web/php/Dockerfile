FROM php:5.6-fpm
RUN apt-get update && apt-get install -y \
        libfreetype6-dev \
        libjpeg62-turbo-dev \
        libmcrypt-dev \
        libpng12-dev \
    && docker-php-ext-install -j$(nproc) iconv mcrypt \
    && docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ \
    && docker-php-ext-install -j$(nproc) gd \
    && docker-php-ext-install zip \
    && docker-php-ext-install mbstring \
    #&& docker-php-ext-configure mysql --with-mysql=mysqlnd  \
    && docker-php-ext-install mysql  \
    #&& docker-php-ext-configure mysqli --with-mysqli=mysqlnd  \
    && docker-php-ext-install mysqli  \
    #&& docker-php-ext-configure pdo_mysql --with-pdo-mysql=mysqlnd  \
    && docker-php-ext-install pdo_mysql \
    && apt-get clean \
    && apt-get autoclean