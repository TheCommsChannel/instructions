# Building your own Digipeater with Le Potato or Raspberry Pi
This is a set of instructions to follow to build your own digipeater using the Libre Computer "Le Potato" device that is similar to a Raspberry Pi. This section is the follow along for video number one of the series.

## Prep
You will need a few things in preperation:
1. A computer (Windows or MacOS)
2. Le Potato board from Libre Computer
3. Power supply for the Le Potato device
4. An ethernet cable to connect the device to your home network. 
5. microSD Card (16GB or 32GB)
6. SD Card Reader (You may already have one if you're using a laptop)
7. A way to scan your WiFi network (We'll be using Fing which is available for both Android and iPhone)


## Downloading & Flashing

### Download the Raspbian Image
The Linux Operating System we'll be loading on the device will be Raspbian. We will need to download it so it can be loaded on the SD Card. The image can be downloaded from the following page - https://distro.libre.computer/ci/raspbian/11/

On this page, you will see a list of available downloads. You need to download the one specific to your device. The device used in the video is LePotato, which is has a model number of AML-S905X-CC. Look on this list for the download containing that, which is currently `2022-09-22-raspbian-bullseye-arm64-lite+aml-s905x-cc.img.xz` Click the link for that and save it to your computer


### Download & Install Raspberry Pi Imager
Next we need a way to flash the Raspbian image to the SD Card. This is done using the Raspberry Pi Imager. Download this by visiting the following link: https://www.raspberrypi.com/software/ and selecting `Download for Windows` or `Download for macOS` if you're on a Mac. 

After the download is done, run it to begin the installation. After the installation is complete, you'll have the option to **Run Raspberry Pi Imager**. Make sure that box is checked and click **Finish**


### Flashing the image
You should now have the Raspberry Pi Imager program open. 

Click on the **Chose Storage** button and take note of what you see (make sure the SD Card you're planning to flash isn't in your computer yet). You may see nothing, or you may see some drives appear. If you do, remember what they are and close the Choose Storage window.

Now, go ahead and insert your SD Card into the computer. Click on the **Choose Storage** button again and take note of what you see. You should see a new device show up. Remember this device. Close the Choose Storage window now.

Click on the **Choose OS** button and scroll down to where you see **Use custom** and click on that. Navigate to the Rasbian Image file you downloaded earlier and double click on it.

Now, click on **Choose Storage** and select the device that showed up after putting the SD card into the computer.

Click on the Gear button to open Advanced Options. Scroll down to the bottom and make sure all of the checkboxes do not have checks in them. Especially **Eject media when finshed**

Click on the **Save** button

Click on the **Write** button

Click on the **YES** button to begin flashing to the SD Card.

When it's done flashing, you can click on the **Continue** button and then close the Raspberry Pi Imager program. You can now also remove the SDcard from the computer.


## Enable SSH and Create User

Unfortunately, Le Potato does not support setting up the user and enabling SSH via the Raspberry Pi Imager Advanced options menu. Not to worry though, it is easy to do manually. Just follow these steps

### Enable SSH
To enable SSH, you simply have to create a file named **ssh** (with no file extension) on the boot directory on the SD Card you just flashed

If you open up the Windows File Explorer, you should see a drive named "boot". Go ahead and open this up. This is where you will need to create the file named **ssh**. Before we do that, we need to make sure we can create the file with not file extension. To do this, click on Start menu and type in **file explorer options** and open that up. Now click on the View tab and look for a checkbox that says "Hide extensions for known file types" if this has a checkmark in it, uncheck it and then hit the **OK** button

Now, back at the drive named "boot" in the Windows File Explorer, you should see a few folders and a bunch of files. Right click on an empty area and select **New** then **Text Document**. You'll see a new file called **New Text Document.txt** appear. Rename this file to **ssh** (Make sure the .txt is gone from the end!) You should see a message pop up saying "If you change a file name extension, the file might become unusable" click on Yes


### Creating a user
Next we need to create a user with username and password. Take the following steps to do This

Just like you did in the previous step, right click on an empty area of the drive named "boot" and select **New** and then **Text Document**. Name this file **userconf.txt** (be sure to include the .txt on this one!)

Double click on this file to open it to edit. This file will need a single line of text that will contain the username you want to use, followed by a colon, then followed by an encrypted version of the password. See the example below

`joe:$6$mwh0rkjDlHnEBZaW$qovFXKDiBXOZ06PhNiB7uuY67gN61t149x/Livd/8HOtUK4.CUertfLX092k9nOYUIp2jRZXK29XvxOz/Jr/R/`

You can change "joe" to whatever you would like your username to be, but keep the encrypted password the same. Go ahead and copy the example above and paste it into the **userconf.txt** file you're editing and change "joe" to whatever you like. Then save the file.


## Booting up, finding the device IP address, and logging on
With those steps complete, the SD Card is ready and can be taken out of the computer by right clicking on the drive named "boot" on File Explorer and clicking **Eject** and then removing the SD Card from your computer.

Insert the card into your Le Potato device, connect the device to your network via the ethernet cable, and now plug the device into the power supply. You should see Blue Green Red lights on the device light up, with the blue one flashing eventually.

### Finding the IP address


### Logging on to the device
To log on, click on the Start menu and type in **terminal** and open up the terminal. Now, type in **ssh yourusername@your-device-ip-address-here** like the example below with the usename joe

`ssh joe@192.168.1.100`

Just replace `joe` and `192.168.1.100` with the username you made in the **userconf.txt** file and `192.168.1.100` with the IP address of your device. Hit enter and then you will be asked to enter in a password. The password is `digipeater`. Type this in and hit enter

You should now be logged into the device and see something like the following

```
Linux raspberrypi 6.0.12-00858-gb98721ea4575 #1 SMP PREEMPT_DYNAMIC Thu Dec 8 19:08:19 UTC 2022 aarch64

The programs included with the Debian GNU/Linux system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Debian GNU/Linux comes with ABSOLUTELY NO WARRANTY, to the extent
permitted by applicable law.
joe@raspberrypi:~ $
```

The first thing you will want to do is change the password. To do this, type in `passwd` and hit enter. You'll be asked to enter in the current password and new password.

# Installing and Configuring Direwolf - Video 2 Instructions
This section is the follow along instructions for Video 2 in the series. In this part, we'll be installing and configuring Direwolf.

## Installing Direwolf

To make the process as easy as possible, I've created a script that you can run that will install all of the prerequisites and direwolf. 

...to be continued
