FROM ubuntu:16.04

RUN DEBIAN_FRONTEND=noninteractive LC_ALL=C.UTF-8 && \
    apt-get update && \
    apt-get dist-upgrade && \
    apt-get install software-properties-common build-essential git curl -y && \
    LC_ALL=C.UTF-8 add-apt-repository ppa:ondrej/php && \
    apt-get update

RUN DEBIAN_FRONTEND=noninteractive && \
    apt-get install -y \
    php7.1 \
    php7.1-intl \
    php7.1-xml \
    php7.1-mysql \
    php7.1-mbstring \
    php7.1-gd \
    php7.1-zip \
    php7.1-imagick \
    php7.1-opcache \
    php7.1-curl \
    php7.1-yaml && \
    update-alternatives --set php /usr/bin/php7.1

RUN DEBIAN_FRONTEND=noninteractive && \
    curl -sL https://deb.nodesource.com/setup_8.x -o nodesource_setup.sh && \
    bash nodesource_setup.sh && \
    apt-get install nodejs -y

RUN npm install -g yarn

RUN php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');" && \
    php composer-setup.php && \
    php -r "unlink('composer-setup.php');" && \
    chmod a+x composer.phar && \
    mv composer.phar /usr/bin/composer
