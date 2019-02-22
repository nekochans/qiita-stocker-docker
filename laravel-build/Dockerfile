FROM php:7.3.2-cli-alpine3.9

RUN set -x && \
  apk update && \
  apk add --no-cache nodejs nodejs-npm libxml2 libxml2-dev curl curl-dev autoconf $PHPIZE_DEPS && \
  docker-php-ext-install mysqli pdo pdo_mysql xml mbstring curl session tokenizer json && \
  curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/bin --filename=composer && \
  composer global require hirak/prestissimo && \
  npm install -g npm && \
  npm install -g yarn && \
  mkdir -p /app

COPY ./config/php.ini /usr/local/etc/php/php.ini

WORKDIR /app
