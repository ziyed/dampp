FROM php:7.2.7-apache

ARG uid
ARG uuser

RUN useradd -G www-data,root -u $uid -d /home/$uuser $uuser
RUN mkdir -p /home/$uuser/.composer && \
    chown -R $uuser:$uuser /home/$uuser

RUN apt-get update --fix-missing -q

RUN apt-get install -y curl mcrypt gnupg build-essential software-properties-common wget vim zip unzip

RUN apt-get --no-install-recommends install -y libreoffice

RUN apt-get install -y ghostscript

RUN apt-get install -y gcc libmagickwand-dev --no-install-recommends \
    && pecl install imagick \
    && docker-php-ext-enable imagick \
    && rm -rf /var/lib/apt/lists/*

RUN docker-php-ext-install pdo pdo_mysql

# Install Node.js
RUN curl -sL https://deb.nodesource.com/setup_13.x | bash
RUN apt-get install --yes nodejs
RUN node -v
RUN npm -v
#RUN npm i -g nodemon
#RUN nodemon -v

# Install Composer
RUN curl -sSL https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

ENV APACHE_DOCUMENT_ROOT=/var/www/html/public
ENV APACHE_LOG_DIR /var/log/apache2
ENV APACHE_RUN_DIR /var/run/apache2
ENV APACHE_LOCK_DIR /var/lock/apache2
ENV APACHE_PID_FILE /var/run/apache2/apache2.pid

RUN sed -ri -e 's!/var/www/html!${APACHE_DOCUMENT_ROOT}!g' /etc/apache2/sites-available/*.conf
RUN sed -ri -e 's!/var/www/!${APACHE_DOCUMENT_ROOT}!g' /etc/apache2/apache2.conf /etc/apache2/conf-available/*.conf

RUN a2enmod rewrite

EXPOSE 80
EXPOSE 443
CMD /usr/sbin/apache2ctl -D FOREGROUND