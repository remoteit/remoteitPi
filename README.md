# Overview
remote.itPi is an SD Card operating system image for Raspberry Pi based on the latest Raspbian OS. The remote.itPi image includes the remote.it application to enable instant remote access to Pi using SSH or VNC and any private network where the Pi is connected.  Once connected to the office network, the Pi will provide direct remote access for authenticated users to any computers, routers, NAS storage boxes, printers, etc. connected to the same remote network.

Download, unzip, and burn the “remote.itPi.img” image file to an SD card, insert it in a Raspberry Pi (any Pi with 512 MB or more RAM) and boot up the Pi. No HDMI display, mouse, or keyboard is needed.  The rootfs partition is automatically expanded to maximize the available space on the SD Card.  SSH and VNC are both enabled by default to allow you to bring up the Pi in a Headless (no monitor, no keyboard, no mouse) configuration from any other computer on the same network.  

Follow the simple steps below to activate remote access to the Pi, and from there, the Pi will provide direct access to any other device, computer, router, printer, NAS storage box, etc. on the same network.

The remote.itPi OS default user is “pi“, password is “raspberry“.  SSH (port 22) and VNC (port 5900/tcp) are both enabled automatically.  Make sure to change the Pi password using the “sudo raspi-config” utility after boot up as described in the detailed step-by-step instructions. A root password is not set by default. If you would like to set the password for root, you can run the command "sudo passwd root" and enter a password of your choosing.

# What you'll need before installing
- [remote.itPi Image .zip](https://downloads.remote.it/pi/latest/remote.itPi.img.zip) downloaded onto your computer
- Formatted micro SD card
- micro SD card reader
- [Raspberry Pi Imager](https://www.raspberrypi.org/downloads/ ) (To write the remote.itPi image onto the micro SD card)

# remote.itPi Installation

If you have already remote.itPi Image, you can see the following <a href="#Preparing-the-remote.itPi-Image">Quick Start remote.itPi image</a>.  
If you use remote.itPi first time, please install remote.itPi by referring to [Preparing the remote.itPi Image](#Preparing-the-remote.itPi-Image) and below.

## Quick Start remote.itPi image
1. Plug in an SD card.  

2. Write the remote.itPi image to the SD card.  

3. Optional: To setup wireless, enter the WiFi credentials into wpa_supplicant.conf on the SD card.  

4. Insert SD card into Pi and turn it on.  

5. Visit http://find.remote.it to find the new Pi.  

6. Connect to your new remote.it device and follow the instructions to create a remote.it account and setup your device
Default OS user credentials:  

- Username: pi  
- Password: raspberry  


## Preparing the remote.itPi Image 
1. Download the [remoteit.Pi Image .zip](https://downloads.remote.it/pi/latest/remote.itPi.img.zip) onto your laptop/desktop if you haven't done so already.

2. Extract the contents of the .zip file onto your computer.

3. Connect your micro SD card reader with the formatted micro SD card inserted to your computer. (If you haven't formatted your micro SD card, you can use Raspberry Pi Imager to do so.)

4. Launch Raspberry Pi Imager. 
- Under "Operating System," click **CHOOSE OS**. When prompted, select the **Use custom** option. Locate and select **remote.itPi.img** that you extracted from the .zip file.
- Under "SD Card," click **CHOOSE SD CARD**. When prompted, select your formatted micro SD card.
- Click **WRITE** to begin writing the remote.itPi image onto the micro SD card. This process will take a few minutes. 

   <img src="https://user-images.githubusercontent.com/42136920/79465318-2543a180-8036-11ea-8a50-a47578932725.png" width="700">

5. If you plan on connecting the remote.itPi device to the internet via Ethernet, you can skip this step and continue to Step 6. If you plan on connecting the remote.itPi device to the internet via Wi-Fi, follow the instructions below:
- Navigate to the micro SD card's **/boot** directory and open **wpa_supplicant.conf** in a text editor. If you don't see the **/boot** directory, you may need to remove the micro SD card from the slot, then re-insert it.
- On the line that says ```ssid="YOUR SSID"```, replace ```YOUR SSID``` with the name of your Wi-Fi network. (Example: ```ssid="MyWiFi123"```)
- On the line that says ```psk="YOUR PASSPHRASE"```, replace ```YOUR PASSPHRASE``` with the password for your Wi-Fi network.(Example: ```psk="P@ssword"```)
- On the line that says ```country=US```, replace ```US``` with your country code. A list of Wi-Fi country codes can be found [here](https://github.com/recalbox/recalbox-os/wiki/Wifi-country-code-(EN)).
- Save the file.
- Locate the **/boot** directory on your computer's file directory.
- Right-click the **/boot** directory to access the menu.
- Click **Eject** to eject the micro SD card reader from your computer.
     
   <img src="https://user-images.githubusercontent.com/42136920/79466585-be26ec80-8037-11ea-866f-b2a86358ca24.png" width="700">
   
## Installing the Image
6. Remove the micro SD card from the card reader and insert it into the remote.itPi. If you are connecting the remote.itPi to the internet via Ethernet, plug the Ethernet cable into the remote.itPi. The other end of the Ethernet cable should connect to an available "LAN" port on your router.
7. Connect a USB power cable to the remote.itPi to power on the Raspberry Pi. 
8. From your computer, open your browser and navigate to: http://find.remote.it. **(Note: Make sure you disable any pop-up blocker extensions or software for the domain "x.remote.it" or this webpage may not load properly.)**  
9. The browser will start to search for your remote.itPi device. If your device isn't detected after the initial search, wait a minute, then click **Search again**.
- Note: If your device isn't detected after a few search attempts, make sure your Wi-Fi credentials are correct in the **wpa_supplicant.conf** file (if the device is connected Wi-Fi) or that the Ethernet is connected properly. 
   <img src="https://user-images.githubusercontent.com/42136920/79466963-368dad80-8038-11ea-8f1b-2e678523d9ce.png" width="700">  

10. After scanning completes, you will see something like "1 of 1" or "1 of 2" above the displayed remote.itPi details.  That represents "(current device) of (total devices)" which were found on your LAN.  The first one may or may not be your Raspberry Pi.  Use the forward ( > ) and back ( < ) arrows to locate your new device if more than one is found.  Once you find your new remote.itPi, click **CONNECT** to connect to it.  
    <img src="https://user-images.githubusercontent.com/42136920/79839988-3ef73700-83f0-11ea-8d2e-fb1d59e1f89f.png" width="700">  

11. You will be prompted to log in to your remote.it account. If you have not created a remote.it account, click "Create an account" to create one.  
    <img src="https://user-images.githubusercontent.com/42136920/79590580-306bff80-8112-11ea-88ae-19bd87faab84.png" width="700">  

12. Once you log in, you will be prompted to register your remote.itPi by providing a name for it. Enter a name, then click **REGISTER**.  
    <img src="https://user-images.githubusercontent.com/42136920/79590723-7032e700-8112-11ea-8a38-7d3d4f3cca97.png" width="700">  
  
    <img src="https://user-images.githubusercontent.com/42136920/80101800-de612900-85ac-11ea-82ae-4b5cc6bab2bc.png" width="700">  
  
    <img src="https://user-images.githubusercontent.com/42136920/80101913-06e92300-85ad-11ea-8709-99c53d958297.png" width="700">  

13. Congratulations! Your remote.itPi is now registered to your remote.it account! You can now connect to your remote.itPi from any device with remote.it installed.  

## Using the remote.it Web Portal
You can also use the [remote.it web portal](https://app.remote.it) to connect to your remote.itPi device. You can view it on the web portal's "Devices" page.  

1. Find your remote.itPi device name and click **CONNECT**.  
   <img src="https://user-images.githubusercontent.com/42136920/80310265-bc69df80-8814-11ea-8634-448f57343bbd.png" width="700">

2. You will see the list of all services available on the remote.itPi device. Click on a service name to start a connection.  
   <img src="https://user-images.githubusercontent.com/42136920/80310358-22566700-8815-11ea-8c5d-d32ead806a2d.png" width="700">

3. When a connection is established, you will see information on how to access the service. Here is an example of the information for accessing the device's graphical desktop using VNC:  
   <img src="https://user-images.githubusercontent.com/42136920/79592414-ee908880-8114-11ea-8320-6e7f0aa28449.png" width="700">

4. Open your VNC client application and enter the provided URL:port to connect to your remote.itPi.  
   <img src="https://user-images.githubusercontent.com/42136920/79641075-332d2a00-81d0-11ea-9ca3-d65935c888be.png" width="700">

5. You will be prompted to enter a username and password. The default login information for remote.itPi is:
- Username: pi  
- Password: raspberry  
   <img src="https://user-images.githubusercontent.com/42136920/79471171-38a63b00-803d-11ea-945c-3cb98a6a2619.png" width="700">

6. You can now access this remote.itPi using VNC from anywhere!
