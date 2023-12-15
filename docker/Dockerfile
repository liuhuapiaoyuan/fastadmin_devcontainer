FROM php:7.4.33-fpm as php



WORKDIR /tmp


RUN php -r "copy('https://install.phpcomposer.com/installer', 'composer-setup.php');"
RUN php composer-setup.php
RUN php -r "unlink('composer-setup.php');"
RUN mv composer.phar /usr/local/bin/composer

# 安装mysql
RUN apt-get update && apt-get install -y \
        libfreetype6-dev \
        libjpeg62-turbo-dev \
        libpng-dev \
        libzip-dev \
        libxml2-dev \
        libmcrypt-dev \
        && docker-php-ext-install -j$(nproc) iconv \
        && docker-php-ext-configure gd --with-freetype --with-jpeg \
        && docker-php-ext-install -j$(nproc) gd \
        && docker-php-ext-install zip \
        && docker-php-ext-install pdo_mysql \
        && docker-php-ext-install mysqli \
        && docker-php-ext-install soap  



# 安装 Nginx 和 Git
RUN apt-get update && \
    apt-get install -y nginx git

# 安装 Docker 和 Docker-Compose
RUN curl -sSL https://get.docker.com/ | sh 

#  清理	
RUN apt-get clean && rm -rf /var/lib/apt/lists/*

COPY ./default.conf /etc/nginx/sites-enabled/default.conf

EXPOSE 80 443

WORKDIR /

# 使用 root 用户运行
USER root

CMD php-fpm -D
