FROM php:8.2-fpm-alpine
RUN apk add --no-cache libzip-dev \
    $PHPIZE_DEPS \
    && docker-php-ext-configure zip \
    && docker-php-ext-install zip
RUN php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');" \
    && php composer-setup.php --install-dir=/usr/local/bin --filename=composer \
    && rm composer-setup.php \
    && pecl install mongodb && docker-php-ext-enable mongodb

