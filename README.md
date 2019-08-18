# FishTankBot2 Board

Setup guide for installing FishTankBot2 board. This board is based off Adafruit Feather M0, with some pin-related changes to SPI library and variants definition, along with updates for lack of crystal oscillator.

### Getting Started

##### 1. Download and install Arduino 15
  * https://www.arduino.cc/en/Guide/HomePage

##### 2. Download custom board and json config
  * https://github.com/ajritch/FishTankBot2
  * in `package_fishtankbot2_index.json`, update the `checksum` and `size` fields
    * [Mac] get checksum from `shasum -a 256 fishtankbot2.zip`
    * [Mac] copy size from `ls -l`
  * in `package_fishtankbot2_index.json`, update the url to the local .zip archive
    * ie `file:///Users/annie/Documents/endiatx/FishTankBot2/fishtankbot2.zip`

##### 3. Install FishTankBot2 in Boards Manager
  * Similar instructions: https://learn.adafruit.com/adafruit-feather-m0-basic-proto/using-with-arduino-ide
  * in Arduino IDE Preferences, add link to "Additional Board Manager URLs" (ie `file:///Users/annie/Documents/endiatx/FishTankBot2/package_fishtankbot2_index.json`)
  * in Arduino IDE Tools -> Board -> Boards Manager, search for the FishTankBot2 board and press "Install"
    * if board doesn't appear in Boards Manager, then the URL was not added properly in preferences
    * if board doesn't appear, but gives CRC Error, then there is an issue with the checksum validation

##### 4. Upload code to the board!

### Documentation for Custom Boards

Guides for setting up custom board files:
* https://forum.arduino.cc/index.php?topic=409715.0
* https://www.hackster.io/wallarug/arduino-ide-creating-custom-boards-89f7a6

Arduino package_index.json formatting details:
* https://github.com/arduino/Arduino/wiki/Arduino-IDE-1.6.x-package_index.json-format-specification

Mac default compression causing troubles:
* https://superuser.com/questions/104500/what-is-macosx-folder/996472#996472


### TODO
* [Mac] checksum validation for .zip archives downloaded from github is failing