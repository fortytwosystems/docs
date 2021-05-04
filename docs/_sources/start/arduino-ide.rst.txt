Arduino IDE Setup
============================

After you've installed the Arduino IDE (v1.6.4 or higher), you'll need to install the board support package. If you've done this before, the board manager URL is:

https://github.com/fortytwosystems/ArduinoCore-samc/releases/download/v1.0.0/package_ArduinoCore-samc_1.0.0_index.json

If this is your first time installing a board support package in the Arduino IDE, follow these steps:

- Open the IDE
- Navigate to File > Preferences
- In the preferences window, under Additional Boards Manager URL, paste the URL shown above. If you have multiple URLs, click the button to the right of
  the input box to open the list.
- Close the preferences window.
- Select Tools > Board > Board Manager from the menu at the top of the IDE
- In the popup window, search for "FortyTwo"
- Install the latest version of the samc core from the list.

Installation may take some time - in addition to the core files, the IDE has to download the full toolchain needed to build the code you write.

Once everything installs, you should see a new set of boards under Tools > Board labeled "FortyTwo Systems SAMC ..." Select the Uno or Mega depending on your board.

Open the Blink example (File > Examples > 01.Basics > Blink) and upload to your board. The LED should toggle on and off every second.