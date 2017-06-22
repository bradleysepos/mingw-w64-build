mingw-w64-build
===============

mingw-w64-build is a Bash script for downloading and building the mingw-w64 toolchain.


Requirements
------------

- Linux, macOS/Darwin, or similar
- Development environment, e.g. autotools, gcc/clang, Xcode


Installation
------------

Copy `mingw-w64-build` to a directory in your `PATH` such as `/usr/local/bin` and make it executable.


Usage
-----

The basic syntax is:

```
mingw-w64-build target [install-dir]
```

Available targets:

- `i686`
- `i686.clean`
- `i686.distclean`
- `x86_64`
- `x86_64.clean`
- `x86_64.distclean`
- `pkgclean`

Default installation directory is `~/toolchains/mingw-w64-<version>-gcc-<gcc_version>`.

Example: build both `i686` and `x86_64` targets, then remove source and build files and downloaded packages, leaving only the output.

```
mingw-w64-build i686 && mingw-w64-build x86_64
mingw-w64-build i686.clean && mingw-w64-build x86_64.clean
mingw-w64-build pkgclean
```

Following successful building of each toolchain, the script provides instructions for adding the output binaries directory to your `PATH`.

To remove the output and start over:

```
mingw-w64-build i686.distclean && mingw-w64-build x86_64.distclean
```

Full usage:

```
mingw-w64-build -h
```


License
-------

Copyright 2017 Bradley Sepos  
Released under the MIT License. See [LICENSE](LICENSE) for details.