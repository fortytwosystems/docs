bossac
==============================================
.. image:: https://img.shields.io/badge/version-5.7.0-brightgreen

https://github.com/fortytwosystems/ArduinoModule-CMSIS

ArduinoModule-CMSIS contains the ARM CMSIS (Cortex Microcontroller Software Interface Standard) 
codebase. See https://developer.arm.com/tools-and-software/embedded/cmsis for more info. Along with
ArduinoModule-CMSIS-Microchip (the vendor-specific stuff), this module forms the backbone of the Arduino SAMC
core.

Build process
-------------

.. note::
    The following build process has only been tested on Windows 10 x86 systems. Your mileage may vary with other
    OS's and architectures.

Prerequisites
+++++++++++++

Start by cloning the repository. You must use the --recursive option to grab the CMSIS_5 repo.

.. code-block:: bash

    git clone --recursive https://github.com/fortytwosystems/ArduinoModule-CMSIS.git

You'll also need to grab the gcc-arm-none-eabi compiler from 
https://developer.arm.com/tools-and-software/open-source-software/developer-tools/gnu-toolchain/gnu-rm/downloads.
We used the 10-2020-q4-major for these instructions. Install it.

You'll need an environment to build in. We used mingw64. Install it if you don't already have it.

DSP Libraries
+++++++++++++
CMSIS contains a number of different DSP libraries, but they don't come pre-compiled for the Cortex-M0+ platform.
You will need to build them. Start by creating a build folder under CMSIS_5/CMSIS/DSP. Go into the folder and create 
a CMakeLists.txt file with the following contents:

.. code-block:: cmake

    cmake_minimum_required (VERSION 3.14)
    # Define the project
    project (buildcmsisdsp VERSION 0.1)

    # Define the path to CMSIS-DSP
    set(DSP ${CMAKE_CURRENT_SOURCE_DIR})

    # Add DSP folder to module path
    list(APPEND CMAKE_MODULE_PATH ${CMAKE_CURRENT_SOURCE_DIR})
    list(APPEND CMAKE_MODULE_PATH ${CMAKE_CURRENT_SOURCE_DIR}/Source)

    ########### 
    #
    # CMSIS DSP
    #

    # Load CMSIS-DSP definitions. Libraries will be built in bin_dsp
    add_subdirectory(${CMAKE_CURRENT_SOURCE_DIR}/Source bin_dsp)

Save the file and run this from the build folder:

.. code-block:: bash

    cmake   -DROOT="../../../.." \
            -DCMAKE_TOOLCHAIN_FILE="../gcc.cmake" \
            -DARM_CPU="cortex-m0plus" \
            -DCMAKE_C_COMPILER="C:/Program Files (x86)/GNU Arm Embedded Toolchain/10 2020-q4-major/bin/arm-none-eabi-gcc.exe" \
            -DCMAKE_CXX_COMPILER="C:/Program Files (x86)/GNU Arm Embedded Toolchain/10 2020-q4-major/bin/arm-none-eabi-gcc.exe" \
            -DCMAKE_MAKE_PROGRAM="make" \ 
            -G "Unix Makefiles" ..

ROOT should be the path to the CMSIS_5 folder.

Finally, run:

.. code-block:: bash

    make VERBOSE=1

Finishing Up
++++++++++++

Go back to the ArduinoModule-CMSIS folder and package everything up by running 

.. code-block:: bash
    
    make all

This should compress relevant files into a tar.bz2 file, and create a package_CMSIS_5.7.0_index.json file which is needed for the Arduino 
package manager. These two files can be uploaded to the file server for download by the Arduino IDE/CLI.

(FortyTwo Systems Internal) tag the release with a "v", followed by the CMSIS version number. 