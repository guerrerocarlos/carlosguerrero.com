---
layout: post-en
title: Lollypop (Android 5.0.1) ROM for Samsung S4 
description: "How to install Android 5.0.1 on Samsung S4”
category: articles
tags: [project]
---

## How to manually install Android 5.0.1 (Lollypop) on Samsung Galaxy S4

First of all, you must download these:

- [Samsung Drivers](https://www.dropbox.com/s/iqyur02m2pbas61/SAMSUNG_USB_Driver_for_Mobile_Phones.zip?dl=://www.dropbox.com/s/iqyur02m2pbas61/SAMSUNG_USB_Driver_for_Mobile_Phones.zip?dl=0) ([original source](http://developer.samsung.com/technical-doc/view.do?v=T000000117))
- [Odin3 (v3.10.6)](https://www.dropbox.com/s/eqtnu1o35mir1nw/Odin3_v3.10.6.zip?dl=0) 
- [Android 5.0.1 for Galaxy S4 firmware](http://www.sammobile.com/firmwares/download/42705/I9500XXUHOA7_I9500SERHOA7_SER.zip/) [alternative torrent download](https://cloudup.com/cmMy0LILnPT)

And obviously you need a computer running Windows, virtualized windows doesn't always work. Else you need to find the Odin3 alternative to your operative system.

## Important: Charge your S4 until having at least 80% of battery available, and make a backup of your files.

# Steps

- Decompress the firmware file
- Turn off your phone and disconnect it from usb cable
- Open Odin3
- Turn on your phone on 'download mode' (-vol + power button + Home)
- Connect the phone to your computer
- You must get a confirmation message on Odin3 saying 'Connected'
- Mark the fields Auto-reboot and F.Reset, *make sure 'Re-Partition' is not marked*.
- Press AP and select the .tar.md5 file that came in the firmware .zip
- This step might take some minutes, since Odin will check for the file to be without errors.
- When the process ends, you will see the word PASS
- The phone will reboot and at the beginning you will see the new Android Lollipop boot.
