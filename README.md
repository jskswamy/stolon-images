## stolon images

Custom docker images for [stolon](https://github.com/sorintlab/stolon)

## Building Images

1. Keeper

```sh
docker build -t local/stolon-keeper:v0.16.0-pg9.6 keeper
```

by default, postgresql v9.6 is used. If you like to use different version use `POSTGRES_VERSION` build args

example:

```sh
# build keeper image for postgresql 10
$ docker build --build-arg POSTGRES_VERSION=10 -t local/stolon-keeper:v0.16.0-pg10 keeper/

# build keeper image for postgresql 11
$ docker build --build-arg POSTGRES_VERSION=11 -t local/stolon-keeper:v0.16.0-pg11 keeper/

# build keeper image for postgresql 12
$ docker build --build-arg POSTGRES_VERSION=12 -t local/stolon-keeper:v0.16.0-pg12 keeper/
```

2. Proxy

```sh
docker build -t local/stolon-proxy:v0.16.0 proxy
```

3. Sentinel

```sh
docker build -t local/stolon-sentinel:v0.16.0 sentinel
```

To build keeper/proxy/sentinel with different version of stolon use `STOLON_VERSION` build args

```sh
# build docker images with stolon version 0.15.0
docker build --build-arg STOLON_VERSION=v0.15.0 -t local/stolon-keeper:v0.15.0-pg9.6 keeper
docker build --build-arg STOLON_VERSION=v0.15.0 -t local/stolon-proxy:v0.15.0 proxy
docker build --build-arg STOLON_VERSION=v0.15.0 -t local/stolon-sentinel:v0.15.0 proxy

# build docker images with stolon version 0.14.0
docker build --build-arg STOLON_VERSION=v0.14.0 -t local/stolon-keeper:v0.14.0-pg9.6 keeper
docker build --build-arg STOLON_VERSION=v0.14.0 -t local/stolon-proxy:v0.14.0 proxy
docker build --build-arg STOLON_VERSION=v0.14.0 -t local/stolon-sentinel:v0.14.0 proxy
```
