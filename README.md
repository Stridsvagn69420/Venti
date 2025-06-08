# Venti
Raspberry Pi Pico weather station

## Hardware
### Microcontroller
This project is primarily developed for the RP2350-based **Raspberry Pi Pico 2W**! <!--And probably the RP2040-based Pico W too!-->
<!--I might add support for ESP32-based boards in the future, as well as nRF-based STM32-based ones. They have to support embassy-rs first though.-->

### Sensors
| Name   | Bus | Address/CS | Data Type                                                           |
| ------ | --- | ---------- | ------------------------------------------------------------------- |
| AS3935 | SPI |            | Lightning                                                           |
| BME280 | SPI |            | Air Pressure, Humidity (AUX), Air Temperature (AUX)                 |
| SHT31  | I2C | `0x44`     | Air Temperature, Humidity                                           |
| SEN55  | I2C | `0x69`     | Particulate Matter, VOC, NOx, Humidity (AUX), Air Temperature (AUX) |
| SCD41  | I2C | `0x62`     | CO2                                                                 |
| RP2350 | ADC | ADC4       | Temperature (CPU)                                                   |

AUX: Sensor can also read this data, but there is already a sensor that does it better.

<!--Will probably add more sensors for WBGT (at least one for the Black Globe)-->

## SDK
Rust, target and toolchain, OpenOCD/probe-rs, udev rules; TBD
