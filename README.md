# docker-blockbook-monacoin

Blockbook Dockerfile for Monacoin

## Usage (directly from Docker Hub)

```
docker run \
    --hostname blockbook \
    -it \
    -v "$(PWD)/db:/blockbook/db" \
    -p 9141:9141 \
    -e RPC_USER=user \
    -e RPC_PASS=pass \
    -e RPC_HOST=127.0.0.1 \
    -e RPC_PORT=9402 \
    -e MQ_PORT=38341 \
    -e TZ=Asia/Tokyo \
    bellflower2015/blockbook-monacoin
```

Blockbook config directory is `/blockbook/config` and database directory is `/blockbook/db`.

You can set environment variables `RPC_USER`, `RPC_PASS`, `RPC_HOST`, `RPC_PORT`, and `MQ_PORT`, and also set `TZ` to change timezone.

If you want to change hostname displayed, you can set it by `--hostname`.

## Build and run instructions

### Build image

Get source code and make docker image:

```
git clone https://github.com/bellflower2015/docker-blockbook-monacoin.git
cd docker-blockbook-monacoin
docker build -t blockbook-monacoin .
```

Docker images are based on Debian 9 (Stretch).

### Run image

Boot from the built image as described below:

```
docker run [options] blockbook-monacoin
```
