# Building your own Digipeater Video 1 Instructions

## Prep
You will need a few things in preperation:
1. A computer (Windows or MacOS)
2. Raspberry Pi (or equivalent.. due to the shortage, we're using the LePotato board from Libre Computer)
3. Power supply for the Raspberry Pi (or equiv) device
4. A way to connect the Raspberry Pi (or equiv) to your home network. Ethernet cable is preferred, but WiFi can be done
5. SD Card (16GB or 32GB)
6. SD Card Reader (You may already have one if you're using a laptop)
7. A way to scan your WiFi network (We'll be using Fing which is available for both Android and iPhone)


## Getting started

### Download the Raspbian Image
The Linux Operating System we'll be loading on the device will be Raspbian. We will need to download it so it can be loaded on the SD Card. The image can be downloaded from the following page - https://distro.libre.computer/ci/raspbian/11/

On this page, you will see a list of available downloads. You need to download the one specific to your device. The device used in the video is LePotato, which is has a model number of AML-S905X-CC. Look on this list for the download containing that, which is currently `2022-09-22-raspbian-bullseye-arm64-lite+aml-s805x-ac.img.xz` Click the link for that and save it to your computer


### Download & Install Raspberry Pi Imager
Next we need a way to flash the Raspbian image to the SD Card. This is done using the Raspberry Pi Imager. Download this by visiting the following link: https://www.raspberrypi.com/software/ and selecting `Download for Windows` or `Download for macOS` if you're on a Mac. 

After the download is done, run it to begin the installation. After the installation is complete, you'll have the option to **Run Raspberry Pi Imager**. Make sure that box is checked and click **Finish**


### Flashing the image
You should now have the Raspberry Pi Imager program open. 

Click on the **Chose Storage** button and take note of what you see (make sure the SD Card you're planning to flash isn't in your computer yet). You may see nothing, or you may see some drives appear. If you do, remember what they are and close the Choose Storage window.

Now, go ahead and insert your SD Card into the computer. Click on the **Choose Storage** button again and take note of what you see. You should see a new device show up. Remember this device. Close the Choose Storage window now.

Click on the **Choose OS** button and scroll down to where you see **Use custom** and click on that. Navigate to the Rasbian Image file you downloaded earlier and double click on it.

Now, click on **Choose Storage** and select the device the showed up after putting the SD card into the computer
