FROM php:7.4.1-apache-buster
LABEL maintainer="yurich84@gmail.com"

COPY . /var/www/html
COPY ./vhost.conf /etc/apache2/sites-available/000-default.conf
COPY ./start.sh /usr/local/bin/start
RUN chmod a+x /usr/local/bin/start

# Installing dependencies
RUN apt-get update && apt-get install -y --no-install-recommends apt-utils \
	zip \
    nano

RUN docker-php-ext-install pdo_mysql

RUN chown -R www-data:www-data /var/www/html \
    && a2enmod rewrite

RUN echo 'alias pa="php artisan"' >> ~/.bashrc

CMD ["/usr/local/bin/start"]
