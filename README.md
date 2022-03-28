# Rainforest Energy Monitoring Component

## Overview
To use your Rainforest Automation EMU-2™ Energy Monitoring Unit in Home Assistant follow the `Installation` and `Configuration` instructions.

## Installation
Place the following files in `config\custom_components\rainforest\`:
* [__`rainforest/__init__.py`__](./__init__.py)
* [__`rainforest/sensor.py`__](./sensor.py)
* [__`rainforest/manifest.json`__](./manifest.json)

## Configuraion
Add the following to your `configuration.yaml` file:

```yaml
# Example configuration.yaml entry
sensor:
  - platform: rainforest
    port: '/dev/ttyACM0'
```

### port:
  * description: The comm port which the meter is connected to.
  * required: true
  * type: string

### name:
  * description: The name to use when displaying this sensor.
  * required: false
  * type: string

## Known Fixes
  * If the emu2 fails to initialize serial (e.g. pi not recognizing it, try different USB cables)
  * If not running HASSIO (e.g. Ubuntu), make sure to have pyserial (via pip3 install pyserial)

## Reference Material
 * https://github.com/smakonin/RAEdataset/blob/master/EMU2_reader.py
 * https://github.com/home-assistant/home-assistant/blob/master/homeassistant/components/sensor/serial.py
 * https://home-assistant.io/components/sensor.date_countdown/
 * https://github.com/rainforestautomation/Emu-Serial-API
