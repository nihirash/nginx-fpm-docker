FROM ubuntu:xenial

# fpm
RUN DEBIAN_FRONTEND="noninteractive" apt-get update && \
				     apt-get -y upgrade && \
 				     apt-get update --fix-missing &&\ 
				     apt-get -y install curl php7.0 php7.0-mysql php7.0-mcrypt php7.0-curl php7.0-mbstring php7.0-soap php7.0-xml php7.0-zip php7.0-gd php7.0-fpm php7.0-json php7.0-mbstring 

COPY php.ini /etc/php/7.0/fpm/
COPY www.conf /etc/php/7.0/fpm/pool.d/
RUN mkdir /run/php
EXPOSE 9000

CMD php-fpm7.0 -F
