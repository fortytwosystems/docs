Tools
=================================================

FortyTwo Systems has assembled a full toolchain for compiling software targeted at the SAMC21/SAMC21N. The toolchain
consists of the following components:

- `ArduinoCore-samc <ArduinoCore-samc.html>`_: A re-write of the Arduino samd core for the SAMC21, heavily inspired 
  by the `mattairtech SAM D/L/C core <https://github.com/mattairtech/ArduinoCore-samd>`_.
- `ArduinoModule-CMSIS-Microchip <ArduinoModule-CMSIS-Microchip.html>`_: Microchip vendor-specific ARM CMSIS package. Pulled from Microchip 
  packs. Includes support for a variety of popular processors.
- `ArduinoModule-CMSIS <ArduinoModule-CMSIS.html>`_: ARM CMSIS package, with DSP modules pre-compiled for Cortex-M0+
- `ArduinoModule-gcc-arm-none-eabi <ArduinoModule-gcc-arm-none-eabi.html>`_: Latest ARM GCC compiler, with custom built version for ARM32 (rpi) architecture. 
  Latest Arduino version is at least 4 years old (!)
- `BOSSAC <bossac.html>`_: tool that is used to flash firmware onto SAM microcontrollers via the bootloader. Custom version
  with support for SAMC21 processors.

Additionally, FortyTwo Systems maintains a full configuration for PlatformIO:

- `platform-atmelsam <platform-atmelsam.html>`_:

.. toctree::
    :maxdepth: 1
    :hidden:

    ArduinoCore-samc
    ArduinoModule-CMSIS-Microchip
    ArduinoModule-CMSIS
    ArduinoModule-gcc-arm-none-eabi
    bossac
    platform-atmelsam