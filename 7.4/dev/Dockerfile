FROM nsign/php-apache:7.4

RUN pecl install https://xdebug.org/files/xdebug-2.9.8.tgz \
    && docker-php-ext-enable xdebug

COPY usr/local/bin/composer.phar /usr/local/bin/composer
RUN chmod +x /usr/local/bin/composer

RUN curl --location --silent --show-error https://github.com/fabpot/local-php-security-checker/releases/download/v2.0.4/local-php-security-checker_2.0.4_linux_amd64 --output /usr/bin/php-security-checker \
    && chmod +x /usr/bin/php-security-checker
