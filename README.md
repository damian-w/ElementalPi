# ElementalPi
ElementalPi is a complete Raspberry Pi (A+ / B+ / 2) weather station solution designed to be as accurate and detailed as possible while maintaining simplicity and ease-of-use. 

### About
This is the code for the ElementalPi project.

### Goals
The ElementalPi project will eventually design, manufacture and produce a Raspberry Pi 40-pin HAT / shield which will be available for individuals (yes, you!) to purchase, construct / solder and utilise in their own environments. ElementalPi will inevitably include three boards: the HAT / shield housing required components, an "air" board housing the temperature / humidity / pressure / air quality equipment, a wind anemometer / direction device and lastly a rain gauge - all connecting to ElementalPi using simple RJ11 telephone cabling.

### What can it sense?
Eventually, ElementalPi will be able to sense:
- Rainfall
- Wind speed
- Wind direction
- Ambient temperature
- Barometric pressure
- Relative humidity
- Light Level
- UV rating
- Air Analysis
-- General quality
-- Carbon Monoxide (CO)
-- Nitrogen Dioxide (NO2)

### Where can I buy one?
ElementalPi is currently under heavy development, and it's expected to be ready for manufacturing in 2016.

---

## Getting Started
To download and start acquiring sensor data, follow this guide below...

### Package Prerequisites
ElementalPi needs several packages to run correctly; ensure you run this command in `sudo`.
`sudo apt-get install build-essential python-pip python-dev python-smbus git`

### Configuring i2c
i2c is an extremely common standard designed simply to allow one computer chip to speak to another. ElementalPi utilises i2c to allow the Raspberry Pi to communicate with [Adafruit's BME280](https://www.adafruit.com/product/2652) breakout. As i2c doesn't come automatically enabled with the RPi, you'll have to follow these steps below to enable it.

#### Enabling i2x
Firstly, you'll need to gather a few prerequisites...
`sudo apt-get install i2c-tools python-smbus`

Then, using RPi's own configuration utility you'll need to enable i2c kernel support...
- `sudo raspi-config`
- Advanced Options
- I2C
- Yes
- Yes
- ... reboot!

#### Testing i2c
After you've installed the prerequisites, enabled i2c and rebooted your RPi, simply type...
`sudo i2cdetect -y 0` or `sudo i2cdetect -y 1`

Shortly after you should see something like this:

```
	 0  1  2  3  4  5  6  7  8  9  a  b  c  d  e  f
00:          -- -- -- -- -- -- -- -- -- -- -- -- -- 
10: -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- 
20: -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- 
30: -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- 
40: -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- 
50: -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- 
60: -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- 
70: -- -- -- -- -- -- -- 77
```

If you see the `77`, then you've done everything right!

### Getting the Code
Now the hard part is done! Clone our code using the below commands to get started!

```
cd ~
git clone https://github.com/damian-w/ElementalPi.git
cd ElementalPi
```

### Configuring ElementalPi
To be written.

### Running ElementalPi
To be written.

---

## Contribute
We appreciate all pull requests! Please don't hesitate to download the code, explore and tinker around.

## Thanks
ElementalPi was inspired by Tom Hartley's work on his discontinued Raspberry Pi weather project, [AirPi](http://airpi.es/).
This project also uses a multitude of Adafruit's Python-based libraries, which are open-source and available [here](https://github.com/adafruit).

## License
Copyright 2015 © [Damian Worsdell](http://djw.net.au/)
ElementalPi is licensed under the [MIT License](http://opensource.org/licenses/MIT).
We fully encourage anyone to download, modify and improve the ElementalPi project.