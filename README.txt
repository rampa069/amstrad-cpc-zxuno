AmstradCPC6128 core
===================

original AmstradCPC464 core (all the hard work), written by Miguel Angel Rodriguez Jodar
enhanced by Microjack with 128kb update, and disk emulation reading / writing from SDcard.

SDCard preparation
------------------
Create a subdirectory in the root folder of the SD card (FAT32 or FAT16) 'AMSTRAD'.  Into
which you should copy the files AMSDOS.ROM and BASIC1-1.ROM.

Keys
----
- F12 - disk menu
- Ctrl-Alt-Delete - reset machine
- Ctrl-Alt-Backspace - reset to BIOS
- END - greenscreen mono mode.
- Scroll Lock - toggle scan doubler on/off

Known issues
------------
- Only 512 byte sector disks supported
- copy protected disks not yet supported - WIP
- Hitting reset randomly moves the screen horizontally sometimes causing the scan lines
  to swap 123456->214365. Keep pressing reset fixes this.  This was a pre-existing issue
  not caused by ctrl-module.
- not 100% compatibility as yet
- scan doubler a little delicate with the mode-R screens

Disk image support
------------------
This supports:
- RAW format, 40 track, 9 sector, 512 byte sectors, and will assume a sequential sector numbering,
  starting from 0xc1.
- CPC Emu extended format, and standard CPC Emu format, limited to 512 byte sector block and no 
  copy protected images at present - WIP.  Maximum 80 tracks 10 sectors and up to 839.5k image size.
- Two disk drives.

Known non-working Games
-----------------------
- DDLE
- Golden Tail
- DeliriumTremens
- Pinball Dreams
- Prehistorik II
- R-Type
- Total Recall

Feedback
--------
zx.micro.jack@gmail.com

ChangeLog
---------
release r1 (candidate)
- ctrl-module to load disks
- booting AMSDOS.ROM from SDcard


