FROM ubuntu:18.04

RUN apt update && apt-get install software-properties-common curl -y
RUN add-apt-repository -y ppa:ondrej/php && apt-get update
RUN apt install nginx php7.4 php7.4-fpm php7.4-common php7.4-mysql php7.4-mbstring php7.4-xml php7.4-zip php7.4-gd \
    php7.4-bcmath php7.4-curl php7.4-sqlite3 php7.4-xdebug supervisor -y && \
    curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer && \
    curl -sL https://deb.nodesource.com/setup_12.x | bash -
RUN apt-get install -y nodejs
RUN apt remove yarn
RUN curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | apt-key add -
RUN echo "deb https://dl.yarnpkg.com/debian/ stable main" | tee /etc/apt/sources.list.d/yarn.list
RUN apt update && apt install -y yarn

RUN openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout /etc/ssl/certs/default.local.key -out /etc/ssl/certs/default.local.crt -subj "/C=CO/ST=Bogota D.C/L=Colombia/O=Defaul/OU=Development/CN=default.local"

EXPOSE 443