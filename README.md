# Pebble development environment

**Updated to pebble-tool-4.5**  ![alt text](https://www.emojibase.com/resources/img/emojis/apple/x203c.png.pagespeed.ic.HxnlpP5g88.png "!!")
**Updated to pebble-sdk-4.3**

## Legal Note
You must accept the [Pebble Terms of Use](https://developer.getpebble.com/legal/terms-of-use/)
and the [SDK License Agreement](https://developer.getpebble.com/legal/sdk-license/) 
to use the Pebble SDK.

## Usage as terminal

Just run:

```sh
PROJECT="Project_Name" && \
docker run -it \
    --net=host \
    --name=P_$PROJECT \
    -e DISPLAY=$DISPLAY \
    -v /tmp/.X11-unix:/tmp/.X11-unix \
    -v ~/.Xauthority:/home/pebble/.Xauthority \
    -v /pathToYourProject/$PROJECT/:/pebble/ \
    manuellr/pebble-dev
```

After you close the shell and the container exit, you can use the restart the 
container with:

```sh
docker start -i -a P_$PROJECT
```

## Before you start

With the Pebble Tool 4.0 and above it is possible to switch the SDK version on the fly.
Based on this change this image will download the latest SDK in the build process.

If you want to use other SDK simply run `pebble sdk install <SDK_VERSION or latest>`.
You can switch between SDK with `pebble sdk activate <SDK_VERSION or latest>`.


## Terminal pebble commands

You can view the commands in the [official page](https://developer.pebble.com/guides/tools-and-resources/pebble-tool).


## Usage not as terminal

Please, read the original code [here](https://hub.docker.com/r/bboehmke/pebble-dev/).


## Compile Dockerfile Manually
```sh
git clone https://github.com/ManuelLR/docker-pebble-dev.git && \
cd docker-pebble-dev && \
sudo docker build -t manuellr/pebble-dev .
```
