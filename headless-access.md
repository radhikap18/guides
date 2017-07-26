# Headless Access to DragonBoard 410c

This guide will teach user to access the DragonBoard 410c without the need of a monitor, i.e. "headless access".

## Hardware Required

1. [DragonBoard 410c](https://www.96boards.org/product/dragonboard410c)
2. [Grove Sensors Mezzanine]()
3. [USB to microUSB cable]()
4. Linux or OSX based Host machine (i.e. personal computer)

## Step 1: Prepare your DragonBoard 410c

In this step we will prepare the DragonBoard 410c to be accessed with your host machine, through "serial console" using the Sensors Mezzanine and a USB to mircoUSB cable. The Sensors Mezzanine and USB cable will act as the interface between your DragonBoard 410c and host machine.

1. DragonBoard 410c is unplugged (powered off)
2. Sensors Mezzanine is connected to DragonBoard 410c through the 40 pin low-speed expansion connector. Mezzanine board (male pins) will match 1-to-1 with female pins on DragonBoard 410c connector. Make sure all 40 pins are lined up properly before moving to next step.
3. Connect USB cable to host machine and microUSB on mezzanine board (USB Type-A end of cable connects to host machine, microUSB end of cable connects to microUSB port on Mezzanine.

> NOTE: Make sure all 40 mezzanine pins (male) are lined up with all 40 input pins (female) on DragonBoard 410c low-speed connetor

> NOTE: USB Type-A to microUSB cable should run from your host machine to the microUSB port on the Sensors Mezzanine, NOT the DragonBoard 410c.

## Step 2: Check device is recognized

In this step we will access the terminal on your host machine to make sure the Mezzanine device (and DragonBoard) are detected by the host machine.

1. DragonBoard is still powered off
2. Open the terminal application on your host machine.
3. Type in the following command:

```shell
$ ls /dev/tty*
```

If a device is detected, you will see a long list of devices. One of these devices should be recognized as the following (or similar):

### Linux:

`ttyUSB0`

### Mac OSX

`tty.usbserial-08-15`

Once you have confirmed your device is being recognized by the host machine, you can move on to the next step.

> NOTE: You may want to unplug and plug back in the USB Type-A end of the cable from you host machine while running the above command in each time. This might help you notice when the device is detected.

## Step 3: Accessing the serial console of your DragonBoard 410c

In this step you will execute a command on your host machine to gain access to your DragonBoard 410c through mezzanine microUSB interface. The following will grant you command line access to the DragonBoard 410c file system.

1. DragonBoard is still powered off
2. Enter the following command:

### Linux

`$ screen /dev/ttyUSB0 115200`

### Mac OSX

`$ screen /dev/tty.usbserial-08-15 115200`

When this command is executed, your terminal will clear and you should only see black.

3. Plug your DragonBoard 410c into power

At this point, the terminal on your host machine should start to print out the boot sequence of your DragonBoard 410c. Once the DragonBoard has finished booting up, you will finally have access to your DragonBoard system through your host machine terminal

Congratulations! You are now accesing your DragonBoard 410c, "Headless"
