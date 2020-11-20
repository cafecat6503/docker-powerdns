FROM debian:buster

RUN echo "deb [arch=amd64 trusted=yes] http://repo.powerdns.com/debian buster-auth-44 main" > /etc/apt/sources.list.d/pdns.list
RUN echo "Package: pdns-*\nPin: origin repo.powerdns.com\nPin-Priority: 600" > /etc/apt/preferences.d/pdns
RUN apt-get update && apt-get install -y pdns-server pdns-backend-mysql

ADD ./pdns.conf /etc/pdns

EXPOSE 53

ENTRYPOINT ["pdns_server","--daemon=no", "--guardian=no", "--loglevel=9"]