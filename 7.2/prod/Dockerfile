FROM nsign/php-apache:7.2

RUN mkdir /opt/tmp && cd /opt/tmp \
    && wget https://github.com/unicode-org/icu/releases/download/release-66-1/icu4c-66_1-src.tgz \
    && tar zxvf icu4c-66_1-src.tgz \
    && cd icu/source \
    && ./configure --prefix=/opt/icu661 && make && make install \
    && rm -rf /opt/tmp

RUN apt-get update \
    && apt-get install --yes --no-install-recommends libicu63 libicu-dev \
    && docker-php-ext-configure intl --with-icu-dir=/opt/icu661 \
    && docker-php-ext-install intl \
    && docker-php-ext-enable intl

RUN apt-get update \
    && apt-get install --yes --no-install-recommends default-mysql-client \
    && docker-php-ext-install pdo_mysql \
    && docker-php-ext-enable pdo_mysql

RUN rm -rf /var/lib/apt/lists/*
