FROM nsign/php-apache:7.4

RUN pecl install https://xdebug.org/files/xdebug-2.9.8.tgz \
    && docker-php-ext-enable xdebug

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer
