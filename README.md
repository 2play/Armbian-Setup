# Armbian-Setup
A setup script to run on top of Armbian Debian in order to set up the necessary drivers and packages to get RetroPie working.

# Setup

1. Download Armbian Stetch (Legacy Kernel 4.4y) from https://www.armbian.com/tinkerboard - https://dl.armbian.com/tinkerboard/Debian_stretch_default.7z
2. Burn the image to an SD card using Etcher (https://etcher.io/)
3. Boot from the SD card. At the login prompt type *root* with password *1234*.
4. You are required to change your password, first enter the root password again *1234*. Then a new password *tinkerboard*.
5. You are now required to create a new user, for ease of compatiblity with Retropie, we will use *pi*. When asked for a password type *tinkerboard*. This has created a new user *pi* with the password *tinkerboard*. When prompted for *Full Name*, *Room Number*, *Work Phone*, *Home Phone* and *Other* just press Enter.
6. To set up WiFi - Type *sudo armbian-config*. Go to *Network* and then *wlan0*. Go to *WiFi* then choose your SSID and enter your password. Don't set up bluetooth or anything yet. Go back to the command prompt once you have an Internet conection.
7. Type *wget https://github.com/2play/Armbian-Tinker-Setup/raw/master/setup2Play.sh*, *sudo chmod 777 setup2play.sh* & *sudo chmod a+x setup2play.sh* and then *./setup2play.sh*.
8. Once everything has installed, run RetroPie-Setup/retropie_setup.sh as indicated in the output of the above script and install core packages and restart.

From Original Notes (optional)
# Bluetooth

After running the setup.sh (which also sets up bluetooth) do the following to complete the process:  
*sudo bluetoothctl*  
[bluetooth]# *agent on*  
Agent registered  
[bluetooth]# *default-agent*  
Default agent request successful  
[bluetooth]# *power on*  
Changing power on succeeded  
[bluetooth]# *exit*  


# Sound over HDMI (Just select N in during the script. Once in ES just plug a headphone to 3.5mm jack and you HSMI sound will start. You can no unplug the headphones.

*sudo nano /usr/share/alsa/alsa.conf*  
Change defaults.pcm.card 0 to 1
