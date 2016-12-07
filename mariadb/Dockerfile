FROM alpine:3.4

RUN apk --update add mysql mysql-client pwgen \
    && rm -rf /tmp/src \
    && rm -f /var/cache/apk/*

ADD scripts/run.sh /scripts/run.sh

RUN mkdir /scripts/pre-exec.d \
    && mkdir /scripts/pre-init.d \
    && chmod -R 755 /scripts

EXPOSE 3306

ENTRYPOINT ["/scripts/run.sh"]
