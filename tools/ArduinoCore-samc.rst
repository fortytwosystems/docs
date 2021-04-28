ArduinoCore-samc
==============================================
.. image:: https://img.shields.io/badge/version-1.0.0-brightgreen

https://github.com/fortytwosystems/ArduinoCore-samc

ArduinoCore-samc contains the core files for Arduino samc support of FortyTwo systems boards.

Build Process
-------------

Start by cloning the repository. The recursive option is currently only mandatory if you plan to run scripts in the :code:`testing` folder

.. code-block:: bash

    git clone --recursive https://github.com/fortytwosystems/ArduinoCore-samc.git

You'll need an environment to build in. We used mingw64. Install it if you don't already have it.

Package everything up by running 

.. code-block:: bash
    
    make

This should compress relevant files into a :code:`tar.bz2` file, and create a :code:`package_ArduinoCore-samc_VERSION_index.json` file which is needed for the Arduino 
package manager. These two files can be uploaded to the file server for download by the Arduino IDE/CLI.