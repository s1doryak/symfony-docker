# docker/php/Dockerfile
FROM php:8.1-cli

RUN curl -1sLf 'https://dl.cloudsmith.io/public/symfony/stable/setup.deb.sh' | bash

RUN apt-get update
RUN apt-get install -y symfony-cli
RUN apt-get install -y openssl zip unzip git curl
RUN apt-get install -y libzip-dev libonig-dev libicu-dev libxml2-dev 
RUN apt-get install -y autoconf pkg-config libssl-dev

RUN docker-php-ext-install bcmath mbstring intl opcache xml
RUN docker-php-ext-install pdo pdo_mysql mysqli

RUN sed -i -e "s/short_open_tag = On/short_open_tag = Off/g" /usr/local/etc/php/php.ini-development
RUN sed -i -e "s/short_open_tag = On/short_open_tag = Off/g" /usr/local/etc/php/php.ini-production

RUN cp /usr/local/etc/php/php.ini-development /usr/local/etc/php/php.ini

ENTRYPOINT [ "symfony" ]

