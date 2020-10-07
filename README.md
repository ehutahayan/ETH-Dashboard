# ETH Dashboard
The dashboard is an up-to-date tracking of your key ETH and Defi indicators. Instead of having to use apps like Blockfolio or websites, you use this code that runs on a Pi with a LCD display. You inmediately see if something happens without haven to wait for a notification from your app. The dashboard includes:<br>
<li> Market: Price, 24hr change and MarketCap, Dominance
<li> Blockchain: average time and fees
<li> Key DeFi indicators. Including BTC locked :-)
<li> Colors: red or green when the change in price per hour is over 1%. 

<img src="https://i.ibb.co/v3Kk5Jr/IMG-20201007-104650.jpg" width="300" alt="IMG-20200930-072821" border="1"><br>

## Hardware
<li>Standard Raspberry Pi 3 or 4
<li>Hyperpixel 3.5" display 
<li>Don't use the default OS supplied by Raspberry. Follow the instructions described below (Install for Hyperpixel)

## What I am currently working on:
1. GitHub stats
2. Automatic screensaver (by time) to save display
3. Automatic start with using variables (for example display switch off/on time)

## Display
<b>Install for HyperPixel 4.0 (3.5" display)</b><br>
    Only follow these instructions. It will save you a lot of time:<br>
    https://learn.pimoroni.com/tutorial/sandyj/getting-started-with-hyperpixel-4<br>

<b>Other displays (not HiperPixel)</b><br>
If you can get them to work, they should be good enough for this project.<br><br>

To rotate the display: <br>
> sudo nano /boot/config.txt
change display_rotate=1 to display_rotate=2<br>
now reboot the machine and the display should be vertical.

## Let the program automatically start after reboot
> crontab -e

insert the following code at the end:<br>
> @reboot DISPLAY=:0 sudo pigpiod<br>
> @reboot DISPLAY=:0 python3 /home/pi/ETHDashboard.py

additional documentation: https://www.raspberrypi.org/documentation/linux/usage/cron.md

## To stop the program
To stop the program, click on the ETH logo. 

## Python
Start the program with "python3" and not "python"  ("python3 ETHDashboard.py")
