FROM php:7.3.9-apache-stretch

# composerのインストール
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

# composerで必要なものとmysql、gd利用のためのパッケージ
RUN apt-get update \
&& apt-get install -y git gnupg unzip \
&& docker-php-ext-install pdo_mysql mysqli mbstring \
&& apt-get clean && rm -rf /var/lib/apt/lists/* \
&& a2enmod rewrite

COPY ./docker/web/php/php.ini /usr/local/etc/php/
COPY ./docker/web/sites-enabled/*.conf /etc/apache2/sites-enabled/
WORKDIR /var/www/html

EXPOSE 80
