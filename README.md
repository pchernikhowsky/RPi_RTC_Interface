# RPi RTC Interface

## Description

A Raspberry Pi HAT-style interface board that includes a:
* DS3231 high-precision real-time clock \(RTC\) with battery backup
* DS18B20 temperature sensor
* 3-pin header terminal for serial tty connection
* Screw terminals connections for a I2C interface
* Screw terminals connections for a 1 Wire interface
<p align="center">
  <img src="Mounted.jpg" alt="Completed hardware"/>
</p>

### Hardware Interfaces

The PCB is designed to mount on a RaspBerry Pi Model 2 or later \(with the 40 pin expansion connecter\).

Two sets of screw terminals are provided:
* A four-terminal I2C connector with 3.3V power, SDA, SCL, and ground. 
* A three-terminal 1 Wire connector with 3.3V power, DQ, and ground.

A 3-pin header connector which provide access to the /dev/ttyS0 is provided.

### Updating Raspbian to support the peripherals

1. sudo apt-get update
2. sudo apt-get upgrade
3. [Configure the kernel and install the necessary RTC packages.](https://pimylifeup.com/raspberry-pi-rtc/)
4. [Enable the 1 Wire interface.](https://www.circuitbasics.com/raspberry-pi-ds18b20-temperature-sensor-tutorial/)

## Hardware Construction and Setup

The schematic and PCB are designed in [KiCad 8.0](https://www.kicad.org/).

A full hardware design including [schematic](schematic.pdf) and PCB layout in KiCad format are provided. I ordered my PCBs from [JLCPCB](https://jlcpcb.com/) and parts from [DigiKey](https://digikey.com), but feel free to use your preferred vendors. 

<p align="center">
  <img src="PCB_front.jpg" alt="PCB front view"/>
  <img src="PCB_rear.jpg" alt="PCB read view"/>
</p>

For diagnostic purposes, one 3.3V power LED is provided. If the 3.3V power output from the I2C or 1 Wire interfaces are overloaded or shorted to ground, the 5V to 3.3V LDO regulator will automatically shutdown (and the LED will extinguish). Removing the overload/short will automatically restore the 3.3V power supply.

## Version history

* 1.0
    * Initial Release

## License

This project is licensed under the GPL-3.0 License. See the [LICENSE](LICENSE) file for details.

## Acknowledgments

Inspiration, code snippets, libraries.
* [RPi_Hat_Template](https://github.com/devbisme/RPi_Hat_Template)

