# experiment-docker-firefox

A test I did to get Firefox running via Docker with a graphical window.


## Build

Assuming `1000` is your current user id and group id. 

```bash
docker build \
    -t firefox \
    --build-arg USER_ID=1000 \
    --build-arg GROUP_ID=1000 \
    .
```

## Run

```bash
docker run \
    -ti \
    --rm \
    -e DISPLAY=$DISPLAY \
    -v /tmp/.X11-unix:/tmp/.X11-unix \
    firefox
```

## Credits

Learned this by reading an article written by [Fábio Rehm](https://github.com/fgrehm):
* http://fabiorehm.com/blog/2014/09/11/running-gui-apps-with-docker
