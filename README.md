Axis
======

Axis is a panoramic rendering engine built for the Littlstar Player. It supports the rendering of
equirectangular, cylindrical, and panoramic textures. It can playback
spherical videos and render panoramic images. It also supports stacked
video produced from the VSN Mobile V.360 video camera. Axis has support for
rendering multiple projections such as Stereoscopic (Oculus), Tiny Planet and
Fisheye.

## Status

Stable

## Installation

Axis can be built and installed in variou ways.

### NPM

Axis is available through *npm*

```sh
$ npm install littlstar/axis --save
```

### Distribution build

Axis is pre-built and available for download in the `dist/` directory of
this repository.

### Source

Axis uses [duo](https://github.com/duojs/duo) internally for installing and
building its dependency components.

```sh
$ git clone git@github.com:littlstar/axis.git
$ cd axis
$ make
```

Distribution builds are now available in the `dist/` directory.
Debug builds are now available in the `build/` directory.

## Example

```js
const axis = requre('littlstar-axis')
const domElement = document.querySelector('#video');
const frame = axis(domElement, {
  src: '/path/to/video.mp4'
});

frame.once('ready', () => {
  frame.seek(5)
  frame.play()
  frame.projection('tiny planet')
  frame.rotate('y', {
    value: 0.002,
    every: 500
  });
});
```

## TODO

* [ ] - Rewrite in ES6
* [ ] - Remove duo/component requirements
* [ ] - Deprecate and start new project without THREE.js dependency.

## Screenshots

### Tiny planet projection

![](public/assets/tiny-planet.png)

### WebVR support

![](public/assets/iceland-oculus.png)

### Littlstar web player

Axis is currently in use in production on the Littlstar web platform.
![](https://www.dropbox.com/s/fzg561w81t1rn3t/Screenshot%202015-07-17%2016.33.26.png?dl=1)

## License

MIT
