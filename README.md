# RUCKUS SmartZone to RUCKUS WAN Gateway Conversion

Welcome! Residing here are the resources I promised to provide in the [video](https://youtu.be/jUeGmDghiNc). Enjoy!

RWG Installer ISO:
[https://drive.google.com/file/d/1LmzsOHr5Gao3FZynjKI2tX_sBINnDU0-/view](https://drive.google.com/file/d/17e9BcbxyPZCFUtzpxJmgyn3V3TDtAfH8/view?usp=drive_link)

Balena Etcher, for flashing the IMG onto the USB:
https://etcher.balena.io

# Flashing the USB on the CLI

If you still want to CLI flash the USB:
```sh
diskutil list
```

Find the disk (`/dev/disk4` in the video) and type:
```sh
diskutil unmountDisk disk4
```

Then zero out and flash (the filename for the IMG file may change!!):
```
sudo dd if=/dev/zero of=/dev/rdisk4 bs=1m count=16
sudo dd if=INSERTFILENAME of=/dev/rdisk4 bs=1m
diskutil eject disk4
```

# Getting into the console port

Find the USB serial device (`/dev/tty.usbserial-A6021H16` for me):
```sh
ls /dev/tty*
```

Open the connection (don't change the 115200; that's the baud rate required by the SZ's console port):
```sh
screen /dev/tty.usbserial-A6021H16 115200
``
