FROM php:8.0-cli

# Apt update
RUN apt-get update --fix-missing

# Install apt-utils
RUN apt-get install -y apt-utils

# Install packages
RUN apt-get install -y \
        git \
        zip \
        curl \
        libzip-dev \
        ca-certificates

# Clear cache
RUN rm -rf /var/lib/apt/lists/*

# Install PHP Extensions
RUN docker-php-ext-install \
    zip

# Install composer
RUN curl -sS https://getcomposer.org/installer -o composer-setup.php \
    && php composer-setup.php --install-dir=/usr/local/bin --filename=composer