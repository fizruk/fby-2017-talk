# miso-aframe-demo

This is a demo project for Miso + A-Frame.

[![Miso + A-Frame demo.](/images/miso-aframe-demo-screenshot.png)][miso-aframe-demo-view]

## About this project

`miso-aframe` is a library binding to JavaScript framework A-Frame,
which allows you to create immersive virtual worlds using WebVR and three.js.

This project demonstrates basic features of `miso-aframe`.
The end result can be seen at
`dist/demo.jsexe/index.html`
([view demo][miso-aframe-demo-view], [view sources][miso-aframe-demo-src]).

[miso-aframe-demo-view]: https://fizruk.github.io/fby-2017-talk/miso-aframe-demo/dist/demo.jsexe/index.html
[miso-aframe-demo-src]:  /miso-aframe-demo/dist/demo.jsexe/index.html

## Requirements

## Requrements

This project is built with [Stack](https://www.haskellstack.org).

Stack can build projects, manage dependencies and install GHC and GHCJS compilers.

### GHCJS

Run this command

```
stack setup
```

This command may take a while (a few hours),
because all packages are built from sources.
Moreover, GHCJS builds its own versions of common packages
after GHCJS itself is ready.

### Node.js

For GHCJSi to work you'll also need [Node.js](https://nodejs.org/en/).

To run things in the browser, install also
`socket.io`, `finalhandler` и `serve-static`:

```
npm install socket.io finalhandler serve-static --global
```

## Build

Run this script to build the project:

```
./build.sh
```

This script will build VR app and will copy necessary static files
(and will replace `index.html` with the right one).

After build the app should open automatically in the browser.

## GHCJSi & interactive browser session

To run GHCSi session run this script:

```
./repl.sh
```

This will run GHCJSi and also a local webserver at
http://localhost:6401 (port can vary for you, see GHCJSi output).

Open this page: http://localhost:6401/ghcjsiClient.html

To (re)load an app, run

```
reloadAFrameApp main
```

If you change sources, you need to reload in GHCJSi:

```
:reload
```

And then restart the app:

```
reloadAFrameApp main
```

## Project stages

This demo project is split into a few steps.
Each stage is represented in sources as `stepN` function, where `N` is stage number.

You can load a particular stage in browser using `reloadAFrameApp`.
For instance, first stage can be loaded like this:

```
reloadAFrameApp step1
```

You can replace `main` implementation with any stage function
to build standalone version of that stage.
