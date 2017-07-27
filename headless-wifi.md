# Connect to WiFi using Terminal (headless or on-board terminal)

This guide will outline two different methods of connecting to a WiFi network with your DragonBoard 410c

- Method one: Connect to WiFi using on-board terminal when running Linaro Debian on your DragonBoard 410c
- Method two: Connect to WiFi while accessing your DragonBoard 410c through external means (serial console or ssh "headless")

## Method one

In this method you will be working directly on the DragonBoard 410c. By the end of this instruction you will have connected to a WiFi network using only a terminal window on your local DragonBoard 410c desktop or developer OS.

1. DragonBoard is running Linaro Debian OS (standard Linux OS)
2. Open Terminal application and execute the following command

`$ nmtui`

This command will open an interactive GUI that will allow you to maneuver your way through the menus and choose your desired WiFi network to connect to. Follow the prompt to connect to a detected WiFi signal.

> NOTE: The DragonBoard 410c is only capable of detecting and connecting to the 2.4GHz WiFi band. If your router does not offer this frequency, the GUI will not show a useable network to connect to.

## Method two

In this method you will be accessing your DragonBoard 410c through a host machine (personal computer, running either Linux or Mac OSX). Please see [headless access](headless-access.md) instructions to learn how to connect to your DragonBoard 410c via serial console using the [Grove Seeed Sensors Mezzanine](https://www.96boards.org/product/sensors-mezzanine/).

1. You are connected to the serial console of your DragonBoard 410c using the Grove Seeed Sensors Mezzanine and a USB Type-A to microUSB cable ([instructions](headless-access.md)
2. Execute the following command:

`$ nmtui`

This command will open an interactive GUI that will allow you to maneuver your way through the menus and choose your desired WiFi network to connect to. Follow the prompt to connect to a detected WiFi signal.

Congratulations! You have connected your DragonBoard 410c to a useable WiFi network using only the command line (Terminal application)
