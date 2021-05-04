BOSSAC
==============================================
.. image:: https://img.shields.io/badge/version-v1.9.1--fortytwo--0-brightgreen

https://github.com/fortytwosystems/BOSSA

BOSSAC (the command line version of BOSSA) is the tool that is used to flash firmware onto SAM 
microcontrollers via the bootloader. FortyTwo Systems has its own version of this utility which 
includes support for the SAMC21/SAMC21N microcontrollers.

Build process
-------------

Prerequisites
+++++++++++++

Start by cloning the repository. You don't need to have wxWidgets installed on your system since you're only building the CLI.

.. code-block:: bash

    git clone https://github.com/fortytwosystems/BOSSA.git

Compile BOSSAC
+++++++++++++++++++++

Navigate into the BOSSA folder. To build the program, run 

.. code-block:: bash
    
    make arduino HOST=hostname

Fill "hostname" according to the following list:

- ARM Linux 32-bit (arm-linux-gnueabihf),
- ARM Linux 64-bit (aarch64-linux-gnu),
- macOS 64-bit (x86_64-apple-darwin),
- Windows (i686-mingw32),
- Linux 32-bit (i686-linux-gnu),
- Linux 64-bit (x86_64-linux-gnu)

To override the version coded into the Makefile, add :code:`VERSION=version` to the above command

Finishing Up
++++++++++++

There should now be a compressed (.tar.bz2) binary in the BOSSA folder, as well as a file 
named :code:`package_bossac_1.9.1-fortytwo-0_hostname_index.json`. Copy and paste the relevant lines 
from that file into the json that should 
have come with the repo. Once you've compiled across all your target operating systems, you
can upload the compressed binaries plus the single json file to your file server.