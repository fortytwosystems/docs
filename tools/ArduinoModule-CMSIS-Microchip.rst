ArduinoModule-CMSIS-Microchip
==============================================
.. image:: https://img.shields.io/badge/version-1.0.0-brightgreen

https://github.com/fortytwosystems/ArduinoModule-CMSIS-Microchip

ArduinoModule-CMSIS-Microchip contains the Microchip vendor-specific ARM CMSIS 
(Cortex Microcontroller Software Interface Standard) codebase. Along with
ArduinoModule-CMSIS (the non-vendor-specific stuff), this module forms the 
backbone of the Arduino SAMC core.

Build process
-------------

.. note::
    The following build process has only been tested on Windows 10 x86 systems. Your mileage may vary with other
    OS's and architectures.

Prerequisites
+++++++++++++

The build process for this module is much simpler than ArduinoModule-CMSIS. Start by cloning the repository.

.. code-block:: bash

    git clone https://github.com/fortytwosystems/ArduinoModule-CMSIS-Microchip.git

You'll need an environment to build in. We used mingw64. Install it if you don't already have it.

Adding processors
+++++++++++++++++

Go to https://packs.download.microchip.com/ and find the processor that you'd like to add. Copy the contents of the archive 
into the CMSIS-Microchip folder.

Finishing Up
++++++++++++

Package everything up by running 

.. code-block:: bash
    
    make all

This should compress relevant files into a :code:`tar.bz2` file, and create a :code:`package_CMSIS-Microchip_VERSION_index.json` file which is needed for the Arduino 
package manager. These two files can be uploaded to the file server for download by the Arduino IDE/CLI.

(FortyTwo Systems Internal) tag the release with a "v", followed by the latest version number. 