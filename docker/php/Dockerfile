FROM php:7.4-fpm

ENV TZ Asia/Tokyo
ENV COMPOSER_ALLOW_SUPERUSER 1

# install Lib for composer
RUN apt-get update -qq && \
  apt-get install --no-install-recommends -y libpq-dev git zip unzip libonig-dev && \
  apt-get clean && \
  rm -rf /var/cache/apt

# RUN docker-php-ext-install mbstring pdo pdo_pgsql

# php.conf php-fpm.conf
# COPY docker/app/conf/php/php.ini /usr/local/etc/php/php.ini
# COPY docker/app/conf/php/docker.conf /usr/local/etc/php-fpm.d/docker.conf
COPY php.ini /usr/local/etc/php/

# install Composer
#Composer install
COPY --from=composer /usr/bin/composer /usr/bin/composer
#RUN curl -sS https://getcomposer.org/installer | php && \
#    mv composer.phar /usr/local/bin/composer && \
#    chmod +x /usr/local/bin/composer

#COPY . /app

# WORKDIR /app
# RUN /usr/local/bin/composer install -d /app

# change owner
RUN chown www-data:www-data -R ./

# ENV COMPOSER_ALLOW_SUPERUSER 1

# ENV COMPOSER_HOME /composer

# ENV PATH $PATH:/composer/vendor/bin

WORKDIR /var/www
