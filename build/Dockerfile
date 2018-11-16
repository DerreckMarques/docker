FROM php:5.6-apache 

#copiando os arquivos necessários
COPY config/ /


RUN  apt-get update    \
     && docker-php-ext-install mysqli \
     #copiando os arquivos de conf do apache
     && cp /000-default.conf /etc/apache2/sites-available/  \ 
     && cp /default-ssl.conf /etc/apache2/sites-available/  \
     && /etc/init.d/apache2 restart




VOLUME ["/var/www/html"]


EXPOSE  80 443 


