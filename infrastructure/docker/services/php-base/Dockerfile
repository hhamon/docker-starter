FROM alpine:3.10

# mirrors in france
RUN echo "http://dl-cdn.alpinelinux.org/alpine/v3.10/main" > /etc/apk/repositories && \
    echo "http://dl-cdn.alpinelinux.org/alpine/v3.10/community" >> /etc/apk/repositories

RUN apk upgrade --no-cache --quiet --available

# Php
RUN apk add --no-cache \
    bash \
    php7 \
    php7-apcu \
    php7-bcmath \
    php7-ctype \
    php7-curl \
    php7-dom \
    php7-iconv \
    php7-intl \
    php7-json \
    php7-mbstring \
    php7-opcache \
    php7-openssl \
    php7-pdo \
    php7-pdo_pgsql \
    php7-pcntl \
    php7-posix \
    php7-session \
    php7-simplexml \
    php7-sockets \
    php7-tokenizer \
    php7-xml \
    php7-xmlwriter \
    php7-zip \
    pcre

# Install fake user app
ARG USER_ID

RUN addgroup --gid 1000 app && \
    adduser --system --uid $USER_ID --home /home/app --shell /bin/bash app

# Configuration
COPY *.ini /etc/php7/conf.d/
