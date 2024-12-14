ARG BUILD_FROM
FROM $BUILD_FROM

ARG EUFY_SECURITY_WS_VERSION

COPY ../../eufy-security-ws/eufy-security-client-3.1.2-beta.tgz /usr/src/app/
COPY ../../eufy-security-ws/eufy-security-ws-1.9.2-beta.tgz /usr/src/app/
WORKDIR /usr/src/app
RUN \
    set -x \
    && apk add --no-cache \
    nodejs \
    npm \
    jq \
    && npm install --force \
      eufy-security-client-3.1.2-beta.tgz \
    && npm install --force \
      eufy-security-ws-1.9.2-beta.tgz
#     "eufy-security-ws@${EUFY_SECURITY_WS_VERSION}"

COPY run.sh /
RUN chmod a+x /run.sh
WORKDIR /data

CMD [ "/run.sh" ]