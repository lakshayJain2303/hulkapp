FROM php:7.3.28-apache

RUN docker-php-ext-install pdo_mysql

RUN a2enmod rewrite

ADD ./bagisto /var/www

ADD ./public /var/www/html

RUN php -r "readfile('http://getcomposer.org/installer');" | php -- --install-dir=/usr/bin/ --filename=composer

RUN chmod 0755 /usr/bin/composer

CMD apachectl -D FOREGROUND
