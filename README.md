# LedFX Docker

> Simple Docker container for [LedFX](https://www.ledfx.app/). <br/>
>
> [`ghcr.io/iganeshk/docker-ledfx:latest`](https://github.com/iganeshk/docker-ledfx/pkgs/container/docker-ledfx) 

Only tested using `/dev/snd/`, should work with pulseaudio as well.

## Tags

- [`latest`](https://github.com/iganeshk/docker-ledfx/pkgs/container/docker-ledfx) - Latest stable release

## Usage

### Docker

```bash
docker run -d \
    --name ledfx \
    --restart=always \

    # instead of binding the port, you can use --net=host
    # which will also allow ledfx to discover your devices
    -p 8888:8888 \

    -e PUID=1000 \
    -e PGID=1000 \

    # e.g give access to a usb sound card
    --device=/dev/snd \
    -v /path/to/config:/home/ledfx/.ledfx/config.json \
    ghcr.io/iganeshk/docker-ledfx:latest
```

## Environment variables

- `PUID` - User ID (default: `1000`)
- `PGID` - Group ID (default: `1000`)
