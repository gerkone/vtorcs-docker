# VTORCS + Docker
This is an all in one package of TORCS, on docker.

The image is already set up with some pre-configured configuration files to allow raw vision deep reinforcement learning input:
* 64x64 resolution
* bumper view
* no HUD
* Removed sound (due to lazyness to fix ALSA)

## Requirements
* Docker
* nvidia-docker toolkit

## Usage

To run this container run
```
nvidia-docker run -v /tmp/.X11-unix:/tmp/.X11-unix:ro -e DISPLAY=unix$DISPLAY -p 3101:3101/udp -it --rm getkone/torcs
```

Then run torcs

Note this will expose the udp port 3101 for external connection, and open a (small) X window with torcs.

## References
The modified TORCS source is taken from [Giuseppe Cuccu's vtorcs](https://github.com/giuse/vtorcs), which enables 64x64 RGB vision.
