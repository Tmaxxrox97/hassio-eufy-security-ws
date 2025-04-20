ARG BUILD_FROM
FROM $BUILD_FROM

ARG EUFY_SECURITY_WS_VERSION

WORKDIR /usr/src/app
RUN \
    set -x \
    && echo "//npm.pkg.github.com/:_authToken= {{ NODE_AUTH_TOKEN }}" > ~/.npmrc \
    && apk add --no-cache\
    nodejs \
    npm \
    jq \
    git \
    openssh-client \
    && npm config set @tmaxxrox97:registry=https://npm.pkg.github.com \
    && npm install --force eufy-security-ws@npm:@tmaxxrox97/eufy-security-ws@1.9.2-beta

COPY run.sh /
RUN chmod a+x /run.sh
WORKDIR /data

CMD [ "/run.sh" ]
