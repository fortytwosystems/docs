Arduino CLI Setup (advanced)
==============================

Using the Arduino CLI (command line interface) to program FortyTwo Systems boards is easy for users familiar with the 
terminal. If you're not familiar with the terminal, you may consider using the `Arduino IDE <arduino-ide.html>`_

Install CLI
--------------------------

Start by installing the CLI on your computer following the `official instructions <https://arduino.github.io/arduino-cli/latest/installation/>`_

Install Core
--------------------------

Once the CLI is on your computer and added to your system PATH, install the fortytwosystems:samc core:

.. code-block:: bash
    
    # Add -v to these commands for verbose mode

    arduino-cli core update-index --additional-urls https://github.com/fortytwosystems/ArduinoCore-samc/releases/download/v1.0.0/package_ArduinoCore-samc_1.0.0_index.json 
    arduino-cli core install fortytwosystems:samc --additional-urls https://github.com/fortytwosystems/ArduinoCore-samc/releases/download/v1.0.0/package_ArduinoCore-samc_1.0.0_index.json

Upload Code
--------------------------

Navigate to the folder where your .ino sketch is located and run the following to compile and upload:

.. code-block:: bash
    
    # Add -v to these commands for verbose mode

    arduino-cli board attach fortytwosystems:samc:mega      # or fortytwosystems:samc:uno
    arduino-cli compile
    arduino-cli upload --port /dev/ttyUSBx  # or COMx for Windows