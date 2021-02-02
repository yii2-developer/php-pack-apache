FROM nsign/php-apache:7.4

RUN pecl install https://xdebug.org/files/xdebug-2.9.8.tgz \
    && docker-php-ext-enable xdebug

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

RUN curl --location --silent --show-error https://github.com/fabpot/local-php-security-checker/releases/download/v1.0.0/local-php-security-checker_1.0.0_linux_amd64 --output /usr/bin/php-security-checker \
    && chmod +x /usr/bin/php-security-checker
