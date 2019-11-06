#FROM openjdk:8-jdk
FROM bitnami/java:1.8-debian-8

ENV OPENFIRE_USER=openfire \
    OPENFIRE_DIR=/usr/local/openfire \
    OPENFIRE_DATA_DIR=/var/lib/openfire \
    OPENFIRE_LOG_DIR=/var/log/openfire \
    OPENFIRE_VERSION=4_3_2

RUN apt-get update -qq \
    && apt-get install -yqq wget sudo \
    && adduser --disabled-password --quiet --system --home $OPENFIRE_DATA_DIR --gecos "Openfire XMPP server" --group openfire

WORKDIR /usr/local/openfire

RUN wget https://www.igniterealtime.org/downloadServlet?filename=openfire/openfire_$OPENFIRE_VERSION.tar.gz -O openfire_$OPENFIRE_VERSION.tar.gz \
    && tar xzvf openfire_$OPENFIRE_VERSION.tar.gz -C $OPENFIRE_DIR --strip-components=1 \
    && chown -R openfire:openfire ${OPENFIRE_DIR} \
    && mv ${OPENFIRE_DIR}/conf ${OPENFIRE_DIR}/conf_org \
    && mv ${OPENFIRE_DIR}/plugins ${OPENFIRE_DIR}/plugins_org \
    && mv ${OPENFIRE_DIR}/resources/security ${OPENFIRE_DIR}/resources/security_org

COPY openfire.xml $OPENFIRE_DIR/conf_org/openfire.xml
COPY entrypoint.sh /sbin/entrypoint.sh
RUN chmod 755 /sbin/entrypoint.sh

EXPOSE 3478/tcp 3479/tcp 5222/tcp 5223/tcp 5229/tcp 5275/tcp 5276/tcp 5262/tcp 5263/tcp 7070/tcp 7443/tcp 7777/tcp 9090/tcp 9091/tcp

VOLUME ["${OPENFIRE_DATA_DIR}"]

CMD ["/sbin/entrypoint.sh"]