FROM busybox

ARG STOLON_VERSION=v0.16.0

EXPOSE 5432

ADD https://github.com/sorintlab/stolon/releases/download/${STOLON_VERSION}/stolon-${STOLON_VERSION}-linux-amd64.tar.gz /tmp/stolon.tar.gz

RUN mkdir -p /usr/local/bin; \
    tar --strip-components=2 -C /usr/local/bin/ -xzf /tmp/stolon.tar.gz stolon-${STOLON_VERSION}-linux-amd64/bin/stolon-sentinel; \
    rm -rf /tmp/stolon.tar.gz
