ArduinoModule-gcc-arm-none-eabi
==============================================
.. image:: https://img.shields.io/badge/version-10--2020--q4--major-brightgreen

https://github.com/fortytwosystems/ArduinoModule-gcc-arm-none-eabi

ArduinoModule-gcc-arm-none-eabi is the module containing the compilers/linkers/etc for ARM embedded 
applications. Everything is pre-compiled, but there is no 32-bit linux ARM edition available without compilation.

Build process
-------------

On the Raspberry Pi, running 32-bit raspbian, download the latest source tarball from https://developer.arm.com/tools-and-software/open-source-software/developer-tools/gnu-toolchain/gnu-rm/downloads

.. code-block:: bash

    sudo apt install p7zip-full build-essential autoconf autogen bison dejagnu flex flip \
        gawk git gperf gzip nsis openssh-client p7zip-full perl \
        python-dev libisl-dev scons tcl texinfo tofrodos wget zip \
        texlive texlive-extra-utils libncurses5-dev \
        gcc-mingw-w64-i686 g++-mingw-w64-i686 binutils-mingw-w64-i686

    mkdir ~/toolchain
    cp ~/Downloads/gcc-arm-none-eabi-10-2020-q4-major-src.tar.bz2 ~/toolchain
    cd ~/toolchain
    tar -xzf gcc-arm-none-eabi-10-2020-q4-major-src.tar.bz2
    cd ./gcc-arm-none-eabi-10-2020-q4-major-source

    ./install-sources.sh
    ./build-prerequisites.sh --skip_steps=mingw32
    ./build-toolchain.sh --skip_steps=howto


Create the required JSON file by running:

.. code-block:: bash
    
    make

This should download each available flavor of the package, compute a checksum and size for each, then 
put all that info into a file called :code:`package_gcc-arm-none-eabi_10-2020q4_index.json`, which is needed for the Arduino 
package manager. Upload this plus the downloaded binaries to the file server for download by the Arduino IDE/CLI.