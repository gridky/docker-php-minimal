FROM php:8.0-cli

RUN apt-get update --fix-missing \
    && apt-get install -y \
        git \
        zip \
        curl \
        ca-certificates \
    && rm -rf /var/lib/apt/lists/*

RUN curl -sS https://getcomposer.org/installer -o composer-setup.php \
    && php composer-setup.php --install-dir=/usr/local/bin --filename=composer