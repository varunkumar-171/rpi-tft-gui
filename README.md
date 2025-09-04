# rpi-tft-gui
A GUI on the TFT display for a headless raspberry pi

This project is a fork of (https://github.com/goodtft/LCD-show.git). I've made some changes to the particular MHS35-show script to ensure 
only the necessary changes take place. The original script messes with a number of system files. 

# Changes Required

The display SKU I use is MHS35. The script included unnecessary configurations to the uart, i2c and a hdmi mode. After these changes the resolution should
become better. Since I installed the lite version and was running a headless version of the raspi, the gui tools also had to be installed

	sudo apt install lightdm              # the graphical login page
	sudo apt install raspberrypi-ui-mods  # the desktop environment 

Run these commands to install them. 

After installation run raspi-config to enable automatic login to the desktop.

Making all these changes and running the script should be enough to get the GUI on the display up and running !

![Raspbian home screen on the rpi tft display](https://github.com/varunkumar-171/rpi-tft-gui/blob/main/disp.jpg)

# RPI FrameBuffer Copy

The RPI output /dev/fb0 is the default output for the GUI's since it has hardware acceleration enabled. Therefore instead of re-directing the GUI to fb1, we will use the rpi-fbcp application to copy the frame from fb0 over to fb1. 

Install the 
	   sudo apt-get install libraspberrypi-dev raspberrypi-kernel-headers
