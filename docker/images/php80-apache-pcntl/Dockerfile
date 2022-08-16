FROM chialab/php-dev:8.0-apache

# Install various PHP extensions
RUN docker-php-ext-configure pcntl --enable-pcntl \
    && docker-php-ext-install pcntl \
    && apt-get update -y \
    && apt-get install -y gcc make autoconf libc-dev pkg-config libssl-dev librabbitmq-dev \
    && pecl install amqp \
    && docker-php-ext-enable amqp \
    && apt-get clean \
    && apt-get autoremove \
    && rm -rf /var/lib/apt/lists/* \
    && rm -rf /tmp/pear
