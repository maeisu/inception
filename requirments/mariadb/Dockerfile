FROM debian:bullseye

RUN apt-get update \
    && apt-get install -y vim mariadb-server

COPY ./init.sh /
RUN chmod +x /init.sh

ENTRYPOINT ["/init.sh"]