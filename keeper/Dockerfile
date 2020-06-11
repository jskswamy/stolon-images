ARG POSTGRES_VERSION=9.6
FROM postgres:${POSTGRES_VERSION}

ARG STOLON_VERSION=v0.16.0

RUN echo "Using POSTGRES_VERSION: ${POSTGRES_VERSION}"
RUN useradd -ms /bin/bash stolon

EXPOSE 5432

ADD https://github.com/sorintlab/stolon/releases/download/${STOLON_VERSION}/stolon-${STOLON_VERSION}-linux-amd64.tar.gz /tmp/stolon.tar.gz

RUN tar --strip-components=2 -C /usr/local/bin/ -xzf /tmp/stolon.tar.gz stolon-${STOLON_VERSION}-linux-amd64/bin/stolon-keeper stolon-${STOLON_VERSION}-linux-amd64/bin/stolonctl; \
    rm -rf /tmp/stolon.tar.gz
