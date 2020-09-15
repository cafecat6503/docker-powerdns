FROM alpine:edge

RUN apk update --no-cache && apk upgrade
RUN apk add pdns --no-cache

ADD ./pdns.conf /etc/pdns

CMD /usr/sbin/pdns_server --daemon=no --guardian=no --loglevel=9