# rpi-AR1100
The program for calibrating the Microchip AR1100 resistive touch screen controller from the Raspberry Pi (Raspbian)
Requires:

`sudo apt-get install git make g++ libusb-1.0-0-dev libgtk2.0-dev`
    
## Installation:

```
git clone https://github.com/PiKeeb/rpi-AR1100
cd rpi-AR1100
make
sudo chmod +x AR1100
```

## Calibration:
    
    Please, note that you can't run the calibration under console/ssh. 
    You requre some desktop enviroment to be installed on your system.
    The following commands can only be run using the Terminal emulator/app on the RPi itself.
    
`sudo ./AR1100 -c 4`

This command will turn the screen white with the `+` sign in the top left corner. 

Tap the center of the `+` sign with some sharp object like a pen or a stylus. Next `+` sign will apear in the ajacent corner of the screen.

Repeat this step for all the `+` signs.

For more accurate calibration you can use 9 or 25 points. For this, run `sudo ./AR1100 -c 9` or `sudo ./AR1100 -c 25` for 9-point and 25-point calibration respectively.

`sudo ./AR1100 -m`

Switches the AR1100 to the USB mouse mode. It's needed to control the mouse cursor

You can also use these commands in combination:

`sudo ./AR1100 -c 9 -m`

Calibrate using 9 points and switch to mouse mode.

## Debugging:

If you want more debugging info you can compile the code with:
```
make clean
make DEBUG=1
```
