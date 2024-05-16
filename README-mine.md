
# macos build

tldr:
```
mkdir build; cd build
cmake .. -DUSE_SYSTEM_QT=1
make -j4
```
https://citra-emulator.com/download/mac/#:~:text=Installing%20Citra%20on%20Mac%20OS,successfully%20installed%20Citra%20on%20MAC!



It’s recommended that you use homebrew to install dependencies. You’ll need to download and install the following to build Citra:

    CMake (brew install cmake)
    A recent version of Xcode and the Xcode command line tools
    Citra Source Code

Using CMake

Create a build folder and generate makefiles for the build:

mkdir build
cd build
cmake ..

Building Citra

make -j4

A citra-qt.app application bundle will now be present under build/bin/. Note that this is non-portable and only works on your machine. You can create distributable bundles as well by running make bundle and checking the output in build/bundle/.
About building on Apple Silicon machines

To build Citra targeting macOS on ARM, the process is largely the same. A few things to note are:

    Make sure the Homebrew version you have installed is the ARM version
    If you are cross-compiling from an x86_64 machine for ARM, when running the cmake command you’ll want to use this command instead:

cmake .. -DCMAKE_OSX_ARCHITECTURES="arm64"

 

    Similarly, if you are cross-compiling from an ARM machine for x86_64, you’ll want to use this command:

cmake .. -DCMAKE_OSX_ARCHITECTURES="x86_64"

