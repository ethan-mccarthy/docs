# Getting Started with the Raspberry Pi

> [!NOTE]
> Instructions for [preparing the Raspberry Pi](https://learn.adafruit.com/pi-thermal-printer) and [configuring CUPS](https://learn.adafruit.com/networked-thermal-printer-using-cups-and-raspberry-pi) are based on the guides produced by Phillip Burgess at Adafruit

#### Prepare SD card with Rasbian
Before customizing avis, prepare the Raspberry Pi by imaging the SD card with the latest version of Raspbian. Visit this tutorial for more instructions. 


#### Enable SSH
Before removing the SD card from the computer you used to flash Raspbian to the SD card, open a text editor (e.g. Sublime Text) and save a blank document with the name `ssh` to the SD card (not in a subdirectory). **Do not add a file extension (e.g. `.txt`) to the filename!** Leave the SD card in the reader for the next step.


#### Configure WiFi
Using the same text editor create another blank document and paste the following (substituting your two-letter country code, WiFi network, and password information):

```
country=US
ctrl_interface=DIR=/var/run/wpa_supplicant GROUP=netdev
update_config=1
 
network={
    ssid="NETWORKNAME"
    psk="NETWORKPASSWORD"
}
```

Then save the document as `wpa_supplicant.conf` to the SD card (don't place this file in a subdirectory).


#### Power and Connect to the Raspberry Pi
Connect the to power (via USB or by wiring the power supply to the Raspberry Pi's power GPIO pins). Give the computer a few moments to boot, then visit your WiFi router's administration webpage to view the Raspberry Pi's IP address.

For macOS users, you may find your router's IP address by opening `System Preferences`, clicking `Network` > `Advanced` > `TCP/IP`. Copy the IP address after `Router:` and paste the address into your web browser. 

Login to the router's webpage (the credentials may be printed on your router or found in the router's user manual). Look around until you see a list of devices connected to the router -- the IP address for the Raspberry Pi should be listed here.

macOS users may connect to the Raspberry Pi via SSH by opening the `Terminal` app and entering the command: `ssh pi@ENTER.Pi.IP.ADDRESS.HERE`

The default password is `raspberry`. *Note: No characters will appear as you type the password — this is normal.*
