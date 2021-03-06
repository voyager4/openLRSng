openLRSng
=========

My fork of openLRS code (based on thUndeadMod of openLRS)

More information at http://openlrsng.org

CONFIGURATOR UTILITY / BINARY FIRMWARE NOTE:
============================================
  This software should be used in source form only by expert users, for normal use 'binary' firmwares can be uploaded and configured by free configuration software available for Windows/Mac/Linux from Chrome web store.

  http://goo.gl/iX7dJx

  Binary firmware images are also available from

  https://github.com/openLRSng/openlrsng.github.com/tree/master/binaries

TRANSMITTER HW:
===============
  - TX_BOARD_TYPE 2 (Arduino Mini/nano 328 16MHz)
    - Flytron openLRS M2 (100mW)/M3(1W) TX
    - OrangeRX UHF TX unit

  - TX_BOARD_TYPE 3 (RX module acting as TX) (Arduino Mini/nano 328 16MHz)
    - Flytron openLRS RX v2
    - OrangeRX UHF RX
    - HawkEye openLRS RX

    - connect PPM input to 5th slot from left (channel 4)
    - button between ground and 4th slot from left (ch3)
    - buzzer via transistor on 3rd slot (ch2) (active high)

  - TX_BOARD_TYPE 4 (Arduino Mini/nano 328 16MHz)
    - openLRSngTX ('kha' or DIY based on ngTX schematics)
    - HawkEye OpenLRSng TX

  - TX_BOARD_TYPE 5 (RX as TX) (Arduino Mini/nano 328 16MHz)
    - DTFUHF/HawkEye 4ch/6ch RX

  - TX_BOARD_TYPE 6 (Arduino Leonardo)
    - DTFUHF/HawkEye deluxe TX

RECEIVER HW:
============
  - RX_BOARD_TYPE 3 (Arduino Mini/nano 328 16MHz)
    - Flytron openLRS RX
    - OrangeRX UHF RX (NOTE both LEDs are RED!!)
    - HawkEye OpenLRS RX

  - RX_BOARD_TYPE 5 (Arduino Mini/nano 328 16MHz)
    - DTFUHF/HawkEye 4ch/6ch RX

  Receiver pin functiontions are mapped using the configurator or CLI interface.

SOFTWARE CONFIGURATION:
=======================
  Only hardware related selections are done in the openLRSng.ino.

  Run time configuration is done by connecting to the TX module (which is put into binding mode) with serial terminal. For best restults use real terminal program like Putty, TeraTerm, minicom(Linux) but it is possible to use Arduino Serial Monitor too.
  Sending '<CR>' (enter) will enter the menu which will guide further. It should be noted that doing edits will automatically change 'RF magic' to force rebinding, if you want to use a specific magic set that using the command (and further automatic changes are ceased for the edit session).

  Datarates are: 0==4800bps 1==9600bps 2==19200bps 3==57600bps 4==125kbps

  Refer to http://openlrsng.org

UPLOADING:
==========
Use a 3v3 FTDI (or other USB to TTL serial adapter) and Arduino >= 1.0.

  o set board to "Arduino Pro or Pro Mini (5V, 16MHz) w/ atmega328" (yes it runs really on 3v3 but arduino does not need to know that)

  o define COMPILE_TX and upload to TX module

  o comment out COMPILE_TX and upload to RX

  o for deluxeTX "arduino boardtype" must be set to "Leonardo"


USERS GUIDE
===========

Please refer to http://openlrsng.org (->wiki)
