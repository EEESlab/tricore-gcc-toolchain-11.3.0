
# Build instructions (Ubuntu)

Clone the repository:

```
git clone --recursive git@github.com:EEESlab/tricore-gcc-toolchain-11.3.0.git
```

Launch the build script:

```
./build-toolchain
```

It is also possible to compile single components of the toolchain.

```
./build-toolchain --build --only binutils-tc
```

For further information on the available options:

```
./build-toolchain --help
```

# Build instructions (Windows 10/11)

Install the MSYS2 environment following the instructions available in the official website: https://www.msys2.org/

Launch a MSYS2 MINGW32 shell from the Start menu

Install the set of packages required for building a GNU toolchain:

```
pacman -S base diffutils texinfo git make automake-wrapper isl-devel mpc-devel mpfr-devel gcc mingw-w64-x86_64-gcc mingw-w64-cross-gcc mingw-w64-i686-isl mingw-w64-i686-mpc mingw-w64-i686-mpfr expect flex bison
```

Set the core.autocrlf property to false (to avoid the automatic convertion of LF endings into CRLF on Git):

```
git config --global core.autocrlf false
```

Clone the repository:

```
git clone --recursive git@github.com:EEESlab/tricore-gcc-toolchain-11.3.0.git
```

Set the path of the directory that will contain the toolchain in the INSTALL_PATH environment variable:

```
export INSTALL_PATH=<absolute path of target directory>
```

Launch the build script:

```
./build-toolchain-msys2 --all
```

