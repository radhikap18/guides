# Accessing GPIO in terminal on DragonBoard 410c

In this guide you will learn to access and manipulate the GPIOs via command line using the built in terminal application on your DragonBoard 410c. For this example you WILL NOT need any particular library.

> NOTE: Before you start this guide, make sure you have identified the 40 pin low-speed expansion connector on your DragonBoard 410c. This connector will looks like a black bar that runs accross one of the longer sides of your board. It will have two rows of 20 pins totaling 40 pins.

For this exercise we are only concerned about the 12 available (And usable) GPIO pins located on this header.

|  410c Signals |PIN|PIN|  410c Signals |
|:--------------|:--|--:|--------------:|
|    GND        |1  |2  |GND            |
|               |3  |4  |               |
|               |5  |6  |               |
|               |7  |8  |               |
|               |9  |10 |               |
|               |11 |12 |               |
|               |13 |14 |               |
|               |15 |16 |               |
|               |17 |18 |               |
|               |19 |20 |               |
|               |21 |22 |               |
|    36         |23 |24 | 12            |
|    13         |25 |26 | 69            |
|    115        |27 |28 | 4             |
|    24         |29 |30 | 25            |
|    35         |31 |32 | 34            |
|    26         |33 |34 | 33            |
|               |35 |36 |               |
|               |37 |38 |               |
|    GND        |39 |40 |GND            |


To access the GPIOs through the Linux shell, open the terminal (start menu > other > LXTerminal; right click this to add shortcut to your desktop if you desire) and give yourself super user access:

```shell
$ sudo su
```

Giving yourself superuser access will allow you to modify the GPIOs (if you get an access denied for a GPIO, this means you’re trying to modify a GPIO the board is using for itself)

Once you have superuser access, navigate to the gpio folder with the following command:

```shell
# cd /sys/class/gpio
```

From within the GPIO folder there are several naming conventions(mentioned above) which can be used to manipulate each function of the GPIO itself.


This will give us the ability to work with a certain GPIO pin - for this example, we will toggle pin 23 which is linked to GPIO_36
```shell
# echo 36 > export
```

This returns the direction of the GPIO
```shell
# cat direction
```

Sets direction of GPIO - for this example, we will set gpio to "out". You can also toggle gpio as "in".
```shell
# echo out > direction
```

This returns 0 if the pin is off, 1 if the pin is on
```shell
# cat value
```

Sets value of GPIO - for this example, we will set the gpio "high" which means "1". You can also toggle gpio as "0:
```shell
# echo 1 > value
```

Using a multimeter set to measuring voltage, you can probe the pin you are toggleing along with one of the ground nodes (Pins 1,2,39, and 40), to watch the voltage switch between ~1.8V and 0V.


