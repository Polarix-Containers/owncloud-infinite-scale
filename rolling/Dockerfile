ARG UID=3004
ARG GID=3004

FROM owncloud/ocis-rolling:latest

LABEL maintainer="Thien Tran contact@tommytran.io"

ARG UID
ARG GID

USER root

RUN apk -U upgrade \    
    && rm -rf /var/cache/apk/*

RUN deluser ocis-user \
    && delgroup ocis-group \
    && addgroup -g ${GID} --system ocis-group \
    && adduser -u ${UID} --ingroup ocis-group --disabled-password --system --home /var/lib/ocis ocis-user \
    && chown -R ocis-user:ocis-group /var/lib/ocis

COPY --from=ghcr.io/polarix-containers/hardened_malloc:latest /install /usr/local/lib/
ENV LD_PRELOAD="/usr/local/lib/libhardened_malloc.so"

USER ocis-user
