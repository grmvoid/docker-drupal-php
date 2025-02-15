FROM grmvoid/php:8.3.16-fpm

LABEL org.opencontainers.image.base.name="docker.io/grmvoid/php:8.3.16-fpm" \
      org.opencontainers.image.description="Application packaged by grmvoid" \
      org.opencontainers.image.documentation="https://github.com/grmvoid/docker-drupal-php/tree/master/README.md" \
      org.opencontainers.image.licenses="MIT" \
      org.opencontainers.image.ref.name="8.3.16-fpm" \
      org.opencontainers.image.source="https://github.com/grmvoid/docker-drupal-php/tree/master/8.3/" \
      org.opencontainers.image.title="drupal-php" \
      org.opencontainers.image.vendor="grmvoid" \
      org.opencontainers.image.version="8.3"

COPY --from=composer:2 /usr/bin/composer /usr/bin/composer

RUN set -eux; \
  apk add --no-cache \
    curl \
    curl-dev \
    freetype-dev \
    icu-dev \
    jpeg-dev \
    libpng-dev \
    libwebp-dev \
    libxml2-dev \
    libzip-dev \
    libjpeg-turbo-dev \
    mariadb-client \
    oniguruma-dev; \
  docker-php-ext-configure gd \
    --with-freetype \
    --with-jpeg \
    --with-webp; \
  docker-php-ext-install \
    bcmath \
    curl \
    exif \
    gd \
    intl \
    mbstring \
    mysqli \
    opcache \
    pdo \
    pdo_mysql \
    soap \
    xml \
    zip; \
  rm -rf /var/cache/apk/* \
    /usr/share/doc \
    /usr/share/man \
    /tmp/*; \