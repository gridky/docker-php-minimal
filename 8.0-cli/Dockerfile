FROM php:8.0-cli

# Apt update
RUN apt-get update --fix-missing

# Install apt-utils
RUN apt-get install -y apt-utils

# Install apt packages
RUN apt-get install -y \
        git \
        zip \
        curl \
        libzip-dev \
        ca-certificates \
        libpng++-dev \
        default-mysql-client

# Install pecl packages
RUN pecl install \
    apcu

# Enable installed extentions
RUN docker-php-ext-enable \
    apcu

# Clear cache
RUN rm -rf /var/lib/apt/lists/*

# Install PHP Extensions
RUN docker-php-ext-install \
    zip \
    pdo_mysql \
    gd \
    exif

# Install composer
RUN curl -sS https://getcomposer.org/installer -o composer-setup.php \
    && php composer-setup.php --install-dir=/usr/local/bin --filename=composer