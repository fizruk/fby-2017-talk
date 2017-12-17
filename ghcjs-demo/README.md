# ghcjs-demo

This is a simple demo project with GHCJS.

## Requrements

This project is built with [Stack](https://www.haskellstack.org).

Stack can build projects, manage dependencies and install GHC and GHCJS compilers.

For GHCJSi to work you will also need [Node.js](https://nodejs.org/en/).

For GHCJSi to communicate with a browser, install `socket.io`:

```
npm install socket.io --global
```

## GHCJS setup

Simple run this command

```
stack setup
```

This command may take a while (a few hours),
because all packages are built from sources.
Moreover, GHCJS builds its own versions of common packages
after GHCJS itself is ready.

## Build

To build the project run

```
stack build
```

## Run GHCJSi

To run GHCJSi:

```
stack repl
```

This command with run GHCJSi and also a local webserver at
http://localhost:6400 (port may change, see GHCJSi output).
Open browser and point it to that address.

To have something displayed on a page, paste this code in GHCJSi session:

```
import GHCJS.Marshal.Pure
documentWrite (pToJSVal "Hello, from Haskell!")
```

