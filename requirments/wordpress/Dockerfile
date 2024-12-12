FROM debian:bullseye

RUN apt-get update \
&& apt-get install -y vim wget unzip curl\
&& apt-get install -y php7.4-fpm php7.4-mysql php7.4-gd php7.4-curl php7.4-xml php7.4-mbstring php7.4-zip \
# && wget https://wordpress.org/latest.zip \
# && unzip latest.zip \

# wp-cliをつかえるようにする
&& curl -O https://raw.githubusercontent.com/wp-cli/builds/gh-pages/phar/wp-cli.phar \
&& chmod +x wp-cli.phar \
&& mv wp-cli.phar /usr/local/bin/wp \

&& mkdir -p /var/www/html \
# && mv ./wordpress/* /var/www/html \
&& mkdir -p /run/php \
&& touch /run/php/php7.4-fpm.pid \
&& chmod 755 /run/php/php7.4-fpm.pid 

COPY ./init.sh /
RUN chmod +x /init.sh

ENTRYPOINT ["/init.sh"]

# ENTRYPOINT ["/bin/sh", "-c", "while :; do sleep 10; done"]

# CMD ["php-fpm7.4", "-F"]