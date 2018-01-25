FROM ubuntu:16.04

RUN DEBIAN_FRONTEND=noninteractive LC_ALL=C.UTF-8 apt-get update && \
    apt-get dist-upgrade && \
    apt-get install software-properties-common -y && \
    LC_ALL=C.UTF-8 add-apt-repository ppa:ondrej/php && \
    apt-get update

RUN DEBIAN_FRONTEND=noninteractive apt-get install -y \
        php \
        php-intl \
        php-xml \
        php-mysql \
        php-mbstring \
        php-gd \
        php-zip \
        php-imagick \
        php7.2-opcache \
        php-curl \
        php-yaml

RUN php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');" && \
    php composer-setup.php && \
    php -r "unlink('composer-setup.php');" && \
    chmod a+x composer.phar && \
    mv composer.phar /usr/bin/composer
