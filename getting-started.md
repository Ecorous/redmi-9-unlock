## Redmi 9 (lancelot/galahad) Bootloader Unlocking (without timer) using `mtkclient`

### Acquiring MTKClient

* Open a cmd window by press `Win+R`, typing cmd, and hitting enter
* Run `git clone https://github.com/bkerler/mtkclient`, and wait for it to finish
* Next, run `cd mtkclient`
* Now `python setup.py install`, then `pip3 install -r requirements.txt` (don't close the command prompt quite yet!)

### Installing MTK VCOM Drivers
* DISABLE DRIVER SIGNATURE VERIFICATION (https://forum.hovatek.com/thread-752.html)
* Download [this file](https://drive.google.com/file/d/0B9srKhKuVIMnalFkV3EzWjVXdUE/view?resourcekey=0-TN-5Ipeegh7SowX4sduz_g) (the button's in the top right)
* Extract the downloaded zip
* Open Device Manager by pressing `Win+X` then selecting device manager
* Select any device group (doesn't matter which, `Mice And Other Pointing Devices` for example)
* Go to the top of the device manager window, select `Action`, then `Add Legacy Hardware`
* The Add hardware wizard will be launched, then click Next
* Select `Install the hardware that I manually select from a list (Advanced)`, then click Next
* Select `Show All Devices`, then click Next
* Select `Have Disk...`
* Select `Browse...` and locate your driver's .inf file then select it (the .inf you're to select is located in \[folder you extracted the zip into\] -> drivers -> USB Vcom driver -> Windows7).
* Select `Open`, then `Ok`
* Select `Mediatek Preloader USB VCOM Port`, then click Next
* Select Next to begin installing the driver (ignore the code 10 error)

### Unlocking the bootloader
* Run `python mtk e metadata,userdata,md_udc` (don't wait for it to finish!) and then connect your Redmi 9 in BROM mode by holding VolDown as you plug it in to your PC
* Run `python mtk da seccfg unlock` and then reconnect your Redmi 9 in BROM mode. 
* Congrats! If you got no errors, you should have an unlocked bootloader
