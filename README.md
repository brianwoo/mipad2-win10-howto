# Xiaomi MiPad2 - How to install Windows 10 from Android

# You will need:
* MiPad2 (16GB or 64GB)
* Windows 10 ISO file (or Ghost Spectre Windows 10 SuperLite ISO)
* Windows 10 Device Drivers (included in this repo)
* [Rufus](https://rufus.ie/en/)
* Double Driver (Google it, or download from this repo)
* 7Zip and WinZip
* 16GB+ USB, USB Hub, USB Mouse and Keyboard

# Step 1 - Download Windows 10
Option 1: Download the Xiaomi Windows 10 recovery (20160125-10586-oobe-16G.zip) from [Archive.org](https://archive.org/download/fr.twb.s_xiaomi_mipad2_factory). You might have to do this if you currently have MIUI installed.

Warning: if you have a 16GB MiPad2, you won't have a lot of space left (maybe 1-2GB left) from this Win10.

Option 2: Download Ghost Spectre Windows 10 SuperLite ISO (with this build, you will have 8GB free space).  Follow this links in the description:
[YouTube](https://youtu.be/B-P1u2LmShc)

Option 3: Download NTLite and repackage Win 10 yourself

# Step 2 - Put Windows 10 on a USB Pendrive
If you choose option 1 from Step 1 above, you can just copy all the files to the USB Pendrive.

Otherwise, for an ISO file, use Rufus to create a USB installer Pendrive for you.

# Step 3 - Put the Double Driver to the USB Pendrive
If you haven't already, download Double Driver from this repo, extract the zip file and put the "Double Driver" folder on your USB Pendrive

# Step 4 - Put the Windows 10 Device Drivers to the USB Pendrive
If  you haven't already, Download the Windows 10 Device Drivers files from this repo.  You will need to use 7zip to extract all the driver files. Put the "win10_drivers" folder on your USB Pendrive

# Step 5 - Install Windows
Plugin the USB Pendrive, USB Mouse and Keyboard to your USB hub. Connect your USB Hub to your MiPad2.

Turn on your tablet and your Windows 10 on your USB Pendrive should start up.  Continue with your Windows 10 installation.

# Step 6 - Install Xiaomi Windows drivers
Once Windows 10 is installed, go to your USB Pendrive via File Explorer, go to the Double Driver, execute dd.exe

Click Restore. Find the Windows 10 Device Drivers you extracted in the Step 4.

Start the driver restore process.

# Step 7 - Fix non-working WiFi
Go to Device Manager, Find Network adapters -> Broadcom 802.11ac Wireless PCIE Full Dongle Adapter.  Go to Properties.

Go to the Driver tab, click Update Driver. Select Browse my computer for drivers.

Select "Let me pick from a list of available drivers on my computer".

Instead of using the Microsoft driver, select the Broadcom driver.

# Step 8 - Fix non-working Camera

## We will need to turn off Secure Boot because the camera driver was not properly signed.
Open CMD as Adminstrator.
Type:
```
bcdedit /set loadoptions DDISABLE_INTEGRITY_CHECKS
```

close the CMD.

Now to the final step (to disable the driver signature enforcement).

This is the simplest way to disable driver signature enforcement on Windows 10 but bear in mind that this method will only disable driver signature temporarily.

To disable driver signature enforcement do the following:

Press and hold the Shift key on your keyboard and click the Restart button.

Choose Troubleshoot > Advanced options > Startup Settings and click the Restart button.
When your computer restarts you’ll see a list of options. Press 7 on your keyboard to select Disable driver signature enforcement.

Your computer will now restart and you’ll be able to install unsigned drivers.

Bear in mind that this method only temporarily disables driver signature enforcement, so be sure to install all the unsigned drivers as soon as you can.

Install the camera driver using Double Driver (win10_drivers\Image\Intel(R) AVStream Camera)



