
## Building GlobalCurrancy (GCY)

### On Ubuntu 14.04

Preparation

Before proceeding to the compilation, the following packages are required:

# refresh ubuntu's repository
sudo apt-get update

#install git
sudo apt-get install git

# install dependencies
sudo apt-get install build-essential cmake libboost1.55-all-dev miniupnpc libunbound-dev graphviz doxygen libdb5.1++-dev
Compilation

We can now download the current GlobalCurrency and compile it as follows:

# download the latest GlobalCurrency source code from github
git clone https://github.com/globalcurrency/gcy.git

# go into globalcurrency folder
cd gcy/

# compile, for compile to finsih succesfully please use a machine with 4GB or more.
make # or make -j number_of_threads, e.g., make -j 2

# Move daemon and wallet to /usr/bin

cd gcy/build/release/src
sudo cp globalcurrencyd /usr/bin
sudo cp simplewallet /usr/bin

# Start Daemon
globalcurrencyd

# Start Wallet
simplewallet


### On *nix

Dependencies: GCC 4.7.3 or later, CMake 2.8.6 or later, and Boost 1.55.

You may download them from:

* http://gcc.gnu.org/
* http://www.cmake.org/
* http://www.boost.org/
* Alternatively, it may be possible to install them using a package manager.

To build, change to a directory where this file is located, and run `make`. The resulting executables can be found in `build/release/src`.

**Advanced options:**

* Parallel build: run `make -j<number of threads>` instead of `make`.
* Debug build: run `make build-debug`.
* Test suite: run `make test-release` to run tests in addition to building. Running `make test-debug` will do the same to the debug version.
* Building with Clang: it may be possible to use Clang instead of GCC, but this may not work everywhere. To build, run `export CC=clang CXX=clang++` before running `make`.

### On Windows
Dependencies: MSVC 2013 or later, CMake 2.8.6 or later, and Boost 1.55. You may download them from:

* http://www.microsoft.com/
* http://www.cmake.org/
* http://www.boost.org/

To build, change to a directory where this file is located, and run theas commands: 
```
mkdir build
cd build
cmake -G "Visual Studio 12 Win64" ..
```

And then do Build.
Good luck!
