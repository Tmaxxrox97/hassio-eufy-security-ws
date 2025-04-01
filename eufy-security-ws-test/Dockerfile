ARG BUILD_FROM
FROM $BUILD_FROM

ARG EUFY_SECURITY_WS_VERSION

WORKDIR /usr/src/app
RUN \
    set -x \
    && apk add --no-cache\
    nodejs \
    npm \
    jq \
    git \
    openssh-client \
    && npm config set registry=https://npm.pkg.github.com \
    && npm install --force @tmaxxrox97/eufy-security-ws@1.9.2-beta

COPY run.sh /
RUN chmod a+x /run.sh
WORKDIR /data

CMD [ "/run.sh" ]
