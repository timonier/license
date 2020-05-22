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
    && apk add --no-cache --no-progress ca-certificates tzdata

COPY --from=license /go/bin/license /usr/bin/license
