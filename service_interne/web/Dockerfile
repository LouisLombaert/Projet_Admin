FROM php:8.0-apache

RUN apt-get update -y
RUN apt-get install -y dnsutils iputils-ping lynx net-tools
RUN apt-get install nano

RUN docker-php-ext-install mysqli pdo pdo_mysql

COPY index.html /var/www/html/index.html
COPY intranet.conf /etc/apache2/sites-available/intranet.conf

RUN a2dissite 000-default.conf
RUN a2ensite intranet.conf

CMD tail -f /dev/null