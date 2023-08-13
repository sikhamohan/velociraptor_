# Velociraptor - Endpoint visibility and collection tool.

Velociraptor is a tool for collecting host based state information
using The Velociraptor Query Language (VQL) queries.

## Quick start

If you want to see what Velociraptor is all about simply:

1. Download the binary from the output folder (windows).

2. Start the GUI

```bash
  $ velociraptor gui
```

This will bring up the GUI, Frontend and a local client. You can
collect artifacts from the client (which is just running on your own
machine) as normal.

## Building from source

To build from source, make sure you have:
 - a recent Golang installed from https://golang.org/dl/ (Currently at least Go 1.17)
   - the `go` binary is in your path.
   - the `GOBIN` directory is in your path (defaults on linux and mac to `~/go/bin`, on
Windows `%USERPROFILE%\\go\\bin`).
 - `gcc` in your path for CGO usage (on Windows, [TDM-GCC](https://jmeubank.github.io/tdm-gcc/about/) has been verified to work)
 - `make`
 - Node.js LTS (the GUI is build using [Node v18.14.2](https://nodejs.org/en/blog/release/v18.14.2))

```bash
    $ git clone https://github.com/Velocidex/velociraptor.git
    $ cd velociraptor

    # This will build the GUI elements. You will need to have node
    # installed first. For example get it from
    # https://nodejs.org/en/download/.
    $ cd gui/velociraptor/
    $ npm install

    # This will build the webpack bundle
    $ make build

    # To build a dev binary just run make.
    # NOTE: Make sure ~/go/bin is on your path -
    # this is required to find the Golang tools we need.
    $ cd ../..
    $ make

    # To build production binaries
    $ make linux
    $ make windows
```

In order to build Windows binaries on Linux you need the mingw
tools. On Ubuntu this is simply:
```bash
$ sudo apt-get install mingw-w64-x86-64-dev gcc-mingw-w64-x86-64 gcc-mingw-w64
```
