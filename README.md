# ESPHome firmware for a DIY More WIFI Plant Sensor

This Repo is forked from github://bruvv/LILYGO-T-Higrow-Esphome/DIYMORE-Plant-Sensor-ESP32.yaml@main

[![Build](https://github.com/odig/DIYMORE-Plant-Sensor-Esp32/actions/workflows/build.yml/badge.svg)](https://github.com/odig/DIYMORE-Plant-Sensor-Esp32/actions/workflows/build.yml)
[![License](https://img.shields.io/github/license/odig/DIYMORE-Plant-Sensor-Esp32.svg)](https://github.com/odig/DIYMORE-Plant-Sensor-Esp32/blob/main/LICENSE)

This [ESPHome](https://esphome.io/) configuration builds firmware for the DIY More plantsensor. It monitors:

- Soil humidity
- Soil Fertilizer
- Temperature
- Humidity

# Requirements

- [ESPHome](https://esphome.io/)

# How to install (easy)

This project automates the building process. So all you need to do is open Chrome, Edge or Opera and go to the [installation page](https://odig.github.io/DIYMORE-Plant-Sensor-Esp32). Connect the ESP32 to your computer via USB and read the instructions on that page.

# How to install (expert)

To use this configuration, adjust the [DIYMORE-Plant-Sensor-ESP32.yaml](https://github.com/odig/DIYMORE-Plant-Sensor-Esp32/blob/main/DIYMORE-Plant-Sensor-ESP32.yaml) and changes the `Subsitions`. If you want to adjust specific settings or do a [calbiration](https://odig.github.io/DIYMORE-Plant-Sensor-Esp32/#how-to-calibrate-the-plant-sensor), the relevant YAML files are in the `common` directory.

After this, flash the firmware to your device, e.g. with:

```
esphome run DIYMORE-Plant-Sensor-ESP32.yaml
```

After you have added your device to Home Assistant ESPHome Integration, the sensors are available in Home Assistant.

# Modularity

This is a modular ESPHome configuration split up in various YAML files that you can import as [packages](https://esphome.io/guides/configuration-types.html#packages).

You can find these in the directory [common](https://github.com/odig/DIYMORE-Plant-Sensor-Esp32/tree/main/common):

[battery.yaml](https://github.com/odig/DIYMORE-Plant-Sensor-Esp32/blob/main/common/battery.yaml)

If you bought a battery and hooked it up to the esp then you will need to enable this in the [DIYMORE-Plant-Sensor-ESP32.yaml](https://github.com/odig/DIYMORE-Plant-Sensor-Esp32/blob/main/DIYMORE-Plant-Sensor-ESP32.yaml). The default battery will run for 12 hours with deep sleep enabled.

[bluetooth.yaml](https://github.com/odig/DIYMORE-Plant-Sensor-Esp32/blob/main/common/bluetooth.yaml)

This will enable bluetooth (proxy) so you can have the bluetooth functionality enabled. Disable when using battery.

[Deepsleep.yaml](https://github.com/odig/DIYMORE-Plant-Sensor-Esp32/blob/main/common/deepsleep.yaml)

If you want to run the battery it is wise to enable this so it will sleep. You can do this in the [DIYMORE-Plant-Sensor-ESP32.yaml](https://github.com/odig/DIYMORE-Plant-Sensor-Esp32/blob/main/DIYMORE-Plant-Sensor-ESP32.yaml)

[dht.yaml](https://github.com/odig/DIYMORE-Plant-Sensor-Esp32/blob/main/common/dht.yaml)

This enables the external temperature sensor that is connected to the board itself to measure the surrounding temperature and humidity.

[plantsensors.yaml](https://github.com/odig/DIYMORE-Plant-Sensor-Esp32/blob/main/common/plantsensors.yaml)

This sets up the sensors that go into the soil itself.

[text_sensors.yaml](https://github.com/odig/DIYMORE-Plant-Sensor-Esp32/blob/main/common/text_sensors.yaml)

When you want to enable the inbuild text_sensors enable this, it will output usefull stuff to home assistant.

