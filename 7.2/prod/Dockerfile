FROM nsign/php-apache:7.2

RUN mkdir /opt/tmp && cd /opt/tmp \
    && wget http://download.icu-project.org/files/icu4c/63.1/icu4c-63_1-src.tgz \
    && tar zxvf icu4c-63_1-src.tgz \
    && cd icu/source \
    && ./configure --prefix=/opt/icu631 && make && make install \
    && rm -rf /opt/tmp

RUN apt-get update \
    && apt-get install -y --no-install-recommends libicu57 libicu-dev \
    && docker-php-ext-configure intl --with-icu-dir=/opt/icu631 \
    && docker-php-ext-install intl \
    && docker-php-ext-enable intl

RUN apt-get update \
    && apt-get install -y --no-install-recommends mysql-client \
    && docker-php-ext-install pdo_mysql \
    && docker-php-ext-enable pdo_mysql

RUN rm -rf /var/lib/apt/lists/*
