# Wbg

Super simple wallpaper application for Wayland compositors
implementing the layer-shell protocol.

Wbg takes a single command line argument: a path to an image
file. This image is displayed scaled-to-fit on all monitors.

More display options, and/or the ability to set a per-monitor
wallpaper _may_ be added in the future.


## Requirements

### Runtime

* pixman
* wayland (_client_ and _cursor_ libraries)
* libpng (optional)
* libjpeg (optional)

Note that at least one of _libpng_ and _libjpeg_ is required.


### Compile time

* Development packages for all the libraries listed under _runtime_.
* wayland-protocols
* [tllist](https://codeberg.org/dnkl/tllist)


## Building

```sh
meson --buildtype=release build
ninja -C build
sudo ninja -C build install
```
