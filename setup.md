# Setting Up

## Development

- `./configure --with-pydebug && make -j`
- `./python.exe -m test -j3`

### Compile

- `Misc/SpecialBuilds.txt` compilation flags
- `Py_DEBUG` use for "pydebug" build to catch common issues

#### Clang

Handy `CFLAGS`

- `-Wno-unused-value`
- `-Wno-empty-body`
- `-Qunused-arguments`
- `-Wno-parentheses-equality` if using clang with ccache
- `-no-integrated-as` if using LLVM 2.8 which is needed to build `ctype` module

### Dependencies

`xcode-select --install`

The above generally works. For macOS Mojave 10.14, the following needs to be executed as well:

```bash
open /Library/Developer/CommandLineTools/Packages/macOS_SDK_headers_for_macOS_10.14.pkg
```

Building with openssl from brew:

```
brew install openssl xz
./configure --with-pydebug --with-openssl=$(brew --prefix openssl)
make -s -j2
```

### make

The CPython Makefile is generated when you run `./configure`.

`Makefile.pre` is used to generate a Makefile specific to your compile system

### [Generic C] Handy compile options

- `-g` debug
- `-Wall` warnings all
- `-O3` or `-O1` optimization levels
