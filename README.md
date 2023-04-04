## USB-CDC-for-MyCloud


This driver allows you to use serial USB devices on some MyCloud devices.
This is the USB CDC-ACM Driver from linux kernel 4.14.22, compiled for intel based MyCloud devices under OS 5 version 5.26.119.
It was built using toolchain : WDMyCloud_PR4100_GPL_v5.26.119_20221229.tar.gz
Available on this page : https://support-en.wd.com/app/products/product-detailweb/p/139

It is provided for : PR4100, PR2100, DL4100, DL2100 (tested only with MyCloud PR4100).
It will NOT work with : EX4100, EX2100, EX4, EX2 Ultra, EX2, Mirror Gen2, Mirror, My Cloud 2.xx, My Cloud 04.xx.
It could probably be compiled for ARM too with little effort, but I haven't tried so far as I don't have such hardware.
More infos on various models here https://support-en.wd.com/app/answers/detailweb/a_id/19649/~/my-cloud%3A-differences-between-models

# How to use
Download the file corresponding to your device.
Login to the management interface of you device.
Go to Applications tab and click "Install an application manually" (wording may vary)
Load the file you downloaded.
Ensure the app is enabled (it should be by default).

The driver will automatically load if the device is rebooted, as long as the app is enabled.
If it was loaded after the device is plugged, it will require replugging the device, or a reboot.

The cdc-acm device(s) will then be available in /dev folder (usually /dev/ttyACM0)
