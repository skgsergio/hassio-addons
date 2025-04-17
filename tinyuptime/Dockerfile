ARG BUILD_FROM=ghcr.io/hassio-addons/base:17.2.4

FROM golang:1.24 AS build

RUN \
    git clone https://github.com/skgsergio/tinyuptime.git /src \
    && cd /src/agent \
    && CGO_ENABLED=0 GOOS=linux go build -o /tinyuptime ./cmd/tinyuptime

# hadolint ignore=DL3006
FROM ${BUILD_FROM}

WORKDIR /opt

SHELL ["/bin/bash", "-o", "pipefail", "-c"]

ARG BUILD_ARCH=amd64

COPY --from=build /tinyuptime /opt/tinyuptime

COPY rootfs /

ARG BUILD_DATE
ARG BUILD_DESCRIPTION
ARG BUILD_NAME
ARG BUILD_REF
ARG BUILD_REPOSITORY
ARG BUILD_VERSION

LABEL \
    io.hass.name="${BUILD_NAME}" \
    io.hass.description="${BUILD_DESCRIPTION}" \
    io.hass.arch="${BUILD_ARCH}" \
    io.hass.type="addon" \
    io.hass.version=${BUILD_VERSION} \
    maintainer="Sergio Conde <skgsergio@gmail.com>" \
    org.opencontainers.image.title="${BUILD_NAME}" \
    org.opencontainers.image.description="${BUILD_DESCRIPTION}" \
    org.opencontainers.image.vendor="Home Assistant Add-ons" \
    org.opencontainers.image.authors="Sergio Conde <skgsergio@gmail.com>" \
    org.opencontainers.image.licenses="GPLv3" \
    org.opencontainers.image.url="https://sconde.net" \
    org.opencontainers.image.source="https://github.com/${BUILD_REPOSITORY}" \
    org.opencontainers.image.documentation="https://github.com/${BUILD_REPOSITORY}/blob/main/README.md" \
    org.opencontainers.image.created=${BUILD_DATE} \
    org.opencontainers.image.revision=${BUILD_REF} \
    org.opencontainers.image.version=${BUILD_VERSION}
