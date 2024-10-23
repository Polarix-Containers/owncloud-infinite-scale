ARG VERSION=5

FROM owncloud/ocis:${VERSION}

LABEL maintainer="Thien Tran contact@tommytran.io"

USER root

RUN apk -U upgrade \    
    && rm -rf /var/cache/apk/*

RUN userdel ocis-user \
    && groupdel ocis-group \
    && addgroup -g 3004 -S ocis-group \
    && adduser -S --ingroup ocis-group --uid 3004 ocis-user --home /var/lib/ocis \
    && chown -R ocis-user:ocis-group /var/lib/ocis

COPY --from=ghcr.io/polarix-containers/hardened_malloc:latest /install /usr/local/lib/
ENV LD_PRELOAD="/usr/local/lib/libhardened_malloc.so"

USER ocis-user