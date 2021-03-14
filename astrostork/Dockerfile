FROM ubuntu:latest

LABEL key="Sergio Barbosa <sbarbosa115@gmail.com>" name="Maintainer"

RUN apt-get update --fix-missing
RUN apt install software-properties-common curl -y
RUN add-apt-repository -y ppa:ondrej/php && apt-get update
RUN apt install nginx php7.4 php7.4-xdebug php7.4-fpm php7.4-common php7.4-common php7.4-pgsql php7.4-mbstring php7.4-xml php7.4-zip php7.4-gd php7.4-curl php7.4-pdo php7.4-sqlite3 supervisor zip -y && \
    curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

WORKDIR /var/www/services/api

EXPOSE 80

CMD ["supervisord"]
