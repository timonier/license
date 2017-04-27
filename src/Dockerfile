FROM alpine:latest

LABEL \
    maintainer="Morgan Auchede <morgan.auchede@gmail.com>"

ENV \
    LICENSE_VERSION=latest

RUN set -eux \

    # Prepare system

    && export GOPATH=/tmp \

    # Install packages

    && apk add --no-cache --no-progress --virtual BUILD_DEPS \
           build-base \
           curl \
           git \
           go \

    && apk add --no-cache --no-progress \
          ca-certificates \

    # Install license

    && export $(curl "https://raw.githubusercontent.com/timonier/version-lister/release/generated/license/${LICENSE_VERSION}" | xargs) \

    && mkdir -p "${GOPATH}/src/github.com/nishanths/license" \
    && git clone "https://github.com/nishanths/license.git" "${GOPATH}/src/github.com/nishanths/license" \
    && git -C "${GOPATH}/src/github.com/nishanths/license" checkout "v${LICENSE_VERSION}" \
    && go get github.com/nishanths/license \
    && mv "${GOPATH}/bin/license" /usr/bin/license \

    # Install dumb-entrypoint

    && curl --location "https://github.com/timonier/dumb-entrypoint/raw/master/bin/installer" | INSTALL_DIRECTORY="/usr/sbin" sh -s install \

    # Clean

    && apk del --no-progress \
           BUILD_DEPS \

    && rm -f -r \
           /tmp/*

ENTRYPOINT [ "dumb-init" , "--" , "dumb-entrypoint" ]
