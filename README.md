# USB-CDC-for-MyCloud


These apps are intended for use on various MyCloud devicesand contain the driver that allows you to use serial USB devices on those NAS.<br>
This is the USB CDC-ACM Driver from linux kernel 4.14.22, compiled for intel based MyCloud devices under OS 5 version 5.26.119, then packaged as an app.<br>
It was built using toolchain WDMyCloud_PR4100_GPL_v5.26.119_20221229, available on this page : https://support-en.wd.com/app/products/product-detailweb/p/139
Source structure for app packaging was borrowed from https://github.com/hashashin/mycloudapps/tree/master/cdc-acm

It is provided for : PR4100, PR2100, DL4100, DL2100 (tested only with MyCloud PR4100).<br>
It will NOT work with : EX4100, EX2100, EX4, EX2 Ultra, EX2, Mirror Gen2, Mirror, My Cloud 2.xx, My Cloud 04.xx.<br>
It could probably be compiled for ARM too with little effort, but I haven't tried so far as I don't have such hardware.<br>
More infos on various models here https://support-en.wd.com/app/answers/detailweb/a_id/19649/~/my-cloud%3A-differences-between-models<br>
I also provide the kernel module alone, it should work equally for PR4100, PR2100, DL4100 and DL2100. 

## How to use
Download the file corresponding to your device.<br>
Login to the management interface of you device.<br>
Go to Applications tab and click "Install an application manually" (wording may vary)<br>
Load the file you downloaded.<br>
Ensure the app is enabled (it should be by default).<br>

### More infos
The driver will automatically load if the device is rebooted, as long as the app is enabled.<br>
If it was loaded after the device is plugged, it will require replugging the device, or a reboot.<br>
The cdc-acm device(s) will then be available in /dev folder (usually /dev/ttyACM0)<br>
The cdc-acm folder contains the source you can use to update the driver/app yourself. To do so, 1st compile the Linux kernel using WD provided chaintool, then update the newly compiled cdc-acm.ko module in the folder. Finally build the app package, still using the WD provided tool.
