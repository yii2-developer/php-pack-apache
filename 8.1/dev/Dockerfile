FROM nsign/php-apache:8.1

RUN pecl install https://xdebug.org/files/xdebug-3.1.6.tgz \
    && docker-php-ext-enable xdebug

COPY usr/local/bin/composer.phar /usr/local/bin/composer
RUN chmod +x /usr/local/bin/composer
