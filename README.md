# Venti
Raspberry Pi Pico weather station

## Hardware
### Microcontroller
This project is primarily developed for the RP2350-based **Raspberry Pi Pico 2W**! <!--And probably the RP2040-based Pico W too!-->
<!--I might add support for ESP32-based boards in the future, as well as nRF-based STM32-based ones. They have to support embassy-rs first though.-->

### Sensors
| Name    | Bus    | Address/CS | Data Type                                                           |
| ------- | ------ | ---------- | ------------------------------------------------------------------- |
| AS3935  | SPI    |            | Lightning Detector                                                  |
| BME280  | SPI    |            | Air Pressure, Humidity (AUX), Air Temperature (AUX)                 |
| SHT31   | I2C    | `0x44`     | Air Temperature, Humidity                                           |
| SEN55   | I2C    | `0x69`     | Particulate Matter, VOC, NOx, Humidity (AUX), Air Temperature (AUX) |
| SCD41   | I2C    | `0x62`     | CO2                                                                 |
| RP2350  | ADC    | ADC4       | Temperature (CPU)                                                   |
| DS18B20 | 1-Wire |            | Black Globe Temperature                                             |

<!-- SHT31 will serve as Dry-Bulb, Wet-Bulb will get calculated using SHT31's T and RH, DS18B20 will serve as Black Globe => WBGT-Index -->
<!-- DRIVER NOTE: I might find some working crates for the Sensirion sensors, but I feel like I have to make most of these myself. I will do that, but they will eventually be exported into a seperate crate. But that will be done after they have been tested and developed in the first place. -->

AUX: Sensor can also read this data, but there is already one that does it better.

I also wanted to add a UV and Ozone sensor as well as an anemometer (windspeed and direction), but no suitable ones are currently available for me.

## SDK
Rust, target and toolchain, OpenOCD/probe-rs, udev rules; TBD
