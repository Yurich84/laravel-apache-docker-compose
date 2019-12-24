FROM php:7.3-fpm-stretch
LABEL maintainer="yurich84@gmail.com"

#COPY ./start.sh /usr/local/bin/start

# Installing dependencies
RUN apt-get update && apt-get install -y --no-install-recommends apt-utils \
    zip \
    nano

# Clear cache
RUN apt-get clean && rm -rf /var/lib/apt/lists/*

# Installing extensions
RUN docker-php-ext-install pdo_mysql

RUN echo 'alias pa="php artisan"' >> ~/.bashrc

# Changing Workdir
WORKDIR /application

#CMD ["/usr/local/bin/start"]
