# Building for PSForever
This version of CryptoPP is meant to be built by GCC.
PSForever started from the CryptoPP located at https://github.com/weidai11/cryptopp.git with the git hash of:

```
commit 20833349d12b2e871782629379d2a5e3293a5d45
Author: weidai <weidai11@users.noreply.github.com>
Date:   Sun Apr 15 22:53:41 2007 +0000
```

This was chosen to match PlanetSide's version of CryptoPP which requires the use of a depreciated Message Authentication Code (MAC) scheme, MD5MAC.

## Building for the local system
Nothing more than GNU Make and a working C++ compiler are required.

```shell
$ make -j4
```

## Cross-compiling
PSForever's servers supports any platform that can run Java. This means that this library must be able to be cross compiled for Windows and Mac.

Here is an example of cross compiling for 64-bit (x86\_64) Windows with the MinGW toolchain:

```shell
$ PREFIX=x86_64-w64-mingw32- make -j4
```

This will produce a `libcryptopp.a` ar archive that needs to be statically linked with the target shared library.
