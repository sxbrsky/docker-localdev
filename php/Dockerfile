FROM alpine:edge

ARG ALPINE_PHP_VERSION=83

RUN set -eux; \
  addgroup -g 1000 docker \
	&& adduser -u 1000 -D -S -G docker docker

RUN set -eux; \
  apk add --update \
    php${ALPINE_PHP_VERSION}-calendar \
    php${ALPINE_PHP_VERSION}-curl \
    php${ALPINE_PHP_VERSION}-ctype \
    php${ALPINE_PHP_VERSION}-dom \
    php${ALPINE_PHP_VERSION}-fileinfo \
    php${ALPINE_PHP_VERSION}-gd \
    php${ALPINE_PHP_VERSION}-pdo \
    php${ALPINE_PHP_VERSION}-pdo_mysql \
    php${ALPINE_PHP_VERSION}-pdo_sqlite \
    php${ALPINE_PHP_VERSION}-phar \
    php${ALPINE_PHP_VERSION}-mbstring \
    php${ALPINE_PHP_VERSION}-simplexml \
    php${ALPINE_PHP_VERSION}-session \
    php${ALPINE_PHP_VERSION}-soap \
    php${ALPINE_PHP_VERSION}-tokenizer \
    php${ALPINE_PHP_VERSION}-zip \
    php${ALPINE_PHP_VERSION}-xml \
    php${ALPINE_PHP_VERSION}-xmlreader \
    php${ALPINE_PHP_VERSION}-xmlwriter \
    php${ALPINE_PHP_VERSION} \
    git; \
  \
    php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"; \
    php composer-setup.php; \
    php -r "unlink('composer-setup.php');"; \
    mv composer.phar /usr/bin/composer