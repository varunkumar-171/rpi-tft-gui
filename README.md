# rpi-tft-gui
A GUI on the TFT display for a headless raspberry pi

This project is a fork of (https://github.com/goodtft/LCD-show.git). I've made some changes to the particular MHS35-show script to ensure 
only the necessary changes take place. The original script messes with a number of system files. 

# Changes Required

The 99-calibration.conf file is incomplete and requires certain changes to it to enable proper framebuffer and X11 config. 

The display SKU I use is MHS35. THe script included unnecessary configurations to the uart, i2c and a hdmi mode. After these changes the resolution should
become better. Since I installed the lite version and was running a headless version of the raspi, the gui tools also had to be installed

	sudo apt install lightdm              # the graphical login page
	sudo apt install raspberrypi-ui-mods  # the desktop environment 

Run these commands to install them. 

After installation run raspi-config to enable automatic login to the desktop.

Making all these changes and running the script should be enough to get the GUI on the display up and running !


