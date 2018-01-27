FROM ubuntu:16.04

RUN DEBIAN_FRONTEND=noninteractive LC_ALL=C.UTF-8 && \
    apt-get update && \
    apt-get dist-upgrade && \
    apt-get install software-properties-common build-essential git curl -y && \
    LC_ALL=C.UTF-8 add-apt-repository ppa:ondrej/php && \
    apt-get update

RUN DEBIAN_FRONTEND=noninteractive apt-get install xvfb libfontconfig xorg wget -y && \
    wget https://github.com/wkhtmltopdf/wkhtmltopdf/releases/download/0.12.4/wkhtmltox-0.12.4_linux-generic-amd64.tar.xz && \
    tar xf wkhtmltox-0.12.4_linux-generic-amd64.tar.xz && \
    rm wkhtmltox-0.12.4_linux-generic-amd64.tar.xz && \
    ln -s /wkhtmltox/bin/wkhtmltopdf /usr/bin/wkhtmltopdf && \
    ln -s /wkhtmltox/bin/wkhtmltoimage /usr/bin/wkhtmltoimaged

RUN DEBIAN_FRONTEND=noninteractive && \
    apt-get install -y \
    php7.2 \
    php7.2-intl \
    php7.2-xml \
    php7.2-mysql \
    php7.2-mbstring \
    php7.2-gd \
    php7.2-zip \
    php7.2-imagick \
    php7.2-opcache \
    php7.2-curl \
    php7.2-yaml && \
    update-alternatives --set php /usr/bin/php7.2

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
