# Venti
Raspberry Pi Pico weather station

## Hardware
### Microcontroller
This project is primarily developed for the **Raspberry Pi Pico W**, though I might switch to the *Pico 2W*. I currently do not plan on adding support for other MCUs.

### Sensors
| Name   | Bus | Address/CS | Data Type                                                           |
| ------ | --- | ---------- | ------------------------------------------------------------------- |
| AS3935 | SPI |            | Lightning                                                           |
| BME280 | SPI |            | Air Pressure, Humidity (AUX), Air Temperature (AUX)                 |
| SHT31  | I2C | `0x44`     | Air Temperature, Humidity                                           |
| SEN55  | I2C | `0x69`     | Particulate Matter, VOC, NOx, Humidity (AUX), Air Temperature (AUX) |
| SCD41  | I2C | `0x62`     | CO2                                                                 |

AUX: Sensor can also read this data, but there is already a sensor that does it better.

## SDK
Rust, target and toolchain, OpenOCD/probe-rs, udev rules; TBD