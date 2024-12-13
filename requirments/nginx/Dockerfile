FROM debian:bullseye

RUN apt-get update && apt-get install -y nginx openssl vim

COPY ./nginx_init.sh /
RUN chmod +x /nginx_init.sh

CMD ["/nginx_init.sh"]
