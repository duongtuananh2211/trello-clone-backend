FROM php:7.4-fpm
RUN apt-get update && apt-get install -y \
                git \
                wget \
                libzip-dev \
                zip \
                unzip \
                curl \
                libssl-dev \
                libxml2-dev \
                libfreetype6-dev \
                libjpeg62-turbo-dev \
                libpng-dev \
                libsodium-dev \
                libmcrypt-dev \
                libmemcached-dev \
                libonig-dev \
    && docker-php-ext-configure gd --with-freetype --with-jpeg \
    && docker-php-ext-install -j$(nproc) gd

RUN docker-php-ext-install pcntl \
    opcache \
    pdo_mysql \
    zip \
    mbstring \
    xml \
    ctype \
    bcmath \
    json \
    tokenizer

RUN echo "INSTALLING COMPOSER..."
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

RUN echo "DONE!"

WORKDIR /var/www/app
COPY . /var/www/app
