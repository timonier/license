FROM golang:alpine as license

RUN set -e -u -x \
\
    # Install packages
\
    && apk add --no-cache --no-progress build-base git \
\
    # Install license
\
    && go get -u github.com/nishanths/license

# ---

FROM alpine:latest

LABEL \
    maintainer="Morgan AUCHEDE <morgan.auchede@gmail.com>"

RUN set -e -u -x \
\
    # Install packages
\
    && apk add --no-cache --no-progress --virtual BUILD_DEPS curl \
    && apk add --no-cache --no-progress bash ca-certificates \
\
    # Install gosu
\
    && curl --location "https://gitlab.com/timonier/dumb-entrypoint/raw/master/src/gosu/installer" | bash -s -- install \
\
    # Clean
\
    && apk del --no-progress BUILD_DEPS \
    && rm -f -r /tmp/*

COPY --from=license /go/bin/license /usr/local/bin/license

COPY rootfs/ /

ENTRYPOINT [ "dumb-entrypoint" ]
