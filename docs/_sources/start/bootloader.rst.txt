Bootloader Flashing
=====================

FortyTwo systems boards come pre-flashed with a serial bootloader connected to the USB port. You should 
never have to burn the bootloader, but in the case that you do, burning a new one is relatively easy.
You will need a JTAG SWD programmer that is compatible with the SAMC21. The Atmel ICE is the best option;
other programmers may work too.

Arduino IDE 
---------------

Start by plugging in the programmer. Make sure that pin 1 is connected to pin 1 on the board. Typically, 
reversing the polarity doesn't do anything bad, but it's better to play it safe.

Go to Tools and select the board you're trying to burn the bootloader to. Next, in the tools menu still,
select the programmer, then hit the Burn Bootloader option. The IDE will burn the bootloader to the board, 
and you're off to the races!

Arduino CLI
---------------

Use the instructions at https://arduino.github.io/arduino-cli/latest/commands/arduino-cli_burn-bootloader/.
The fqbn option should be set to fortytwosystems:samc:uno/mega