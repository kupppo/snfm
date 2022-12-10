# Super Nintendo File Manager
A tool for interacting with the file system on your SNES via [SNI](https://github.com/alttpo/sni).

## Installation
To install SNFM, first clone the repository and its submodules.
```sh
# HTTPS
git clone --recursive https://github.com/zig-for/snfm.git

# SSH
git clone --recursive git@github.com:zig-for/snfm.git

# Github CLI
gh repo clone zig-for/snfm -- --recursive
```

If you have already cloned the repository but did not fetch the submodules, then you will need to do so with the following command.
```sh
git submodule update --init --recursive
```

## Dependencies
The following depdencies must be installed.
* [protobuf](https://github.com/protocolbuffers/protobuf/)
* [grpc](https://grpc.io/)
* [wxwidgets](https://www.wxwidgets.org/)

On Windows, this is handled via [Vcpkg](https://vcpkg.io/).

On MacOS, this can be done via [Homebrew](https://brew.sh/).

For Linux, this must be done manually.

## Build
### Windows

```sh
# Use Vcpkg to install dependencies
vcpkg install protobuf:x64-windows grpc wxwidgets

# Use CMake to create the initial setup
cmake -B build -S . "-DCMAKE_TOOLCHAIN_FILE=<YOUR_VCPKG_INSTALL_FOLDER>/scripts/buildsystems/vcpkg.cmake"

# Use CMake to create your build
cmake --build build
```

### MacOS
```sh
# Install dependencies via Homebrew
brew install protobuf grpc wxwidgets

# Use CMake to create the initial setup
cmake -B build -S .

# Use CMake to create your build
cmake --build build
```

### Linux
The same, but install the dependencies through git/apt. Good luck.
