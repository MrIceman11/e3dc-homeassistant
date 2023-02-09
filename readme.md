# E3DC to Home Assistant

This is a custom configuration for Home Assistant to read data from an E3DC device via ModBus.

## Installation

Copy on your Home Assistant server the folder `packages` at the same level of the `configuration.yaml` file.

## Configuration

Add the following line to your `configuration.yaml` file:

```homeassistant:
  customize_glob: !include packages/customize_global.yaml

modbus: !include packages/e3dc.yaml
binary_sensor: !include packages/binary_sensors.yaml
sensor: !include packages/sensors.yaml
```

Edit the file `packages/e3dc.yaml` and add your E3DC device IP address.

## Usage

Restart Home Assistant and you will find the sensors in the `e3dc` entity. Now you can use them in your automations or add the sensors to your dashboard.
If your add HACS to your Home Assistant, you can add the Layout called [Power-Distribution-Card](https://github.com/JonahKr/power-distribution-card)

To Add the Sensor to your Energy Dashboard use the following Sensors:

<img src="[https://github.com/MrIceman11/e3dc-homeassistant/blob/main/examples/Dashboard_Config.png?raw=true](https://github.com/MrIceman11/e3dc-homeassistant/blob/main/examples/Dashboard_Config_2.png?raw=true)"/>

It is normal that some sensors are not available. This is because the E3DC device has not yet sent all the values. This can take up to 2 days.

## Sensors

The following sensors are available: (not completed!!)

  * `e3dc_battery_charge` - Battery charge in percent
  * `e3dc_battery_discharge` - Battery discharge in percent
  * `e3dc_battery_power` - Battery power in Watt
  * `e3dc_battery_voltage` - Battery voltage in Volt
  * `e3dc_grid_power` - Grid power in Watt
  * `e3dc_grid_voltage` - Grid voltage in Volt
  * `e3dc_home_power` - Home power in Watt
  * `e3dc_home_voltage` - Home voltage in Volt
  * `e3dc_pv_power` - PV power in Watt
  * `e3dc_pv_voltage` - PV voltage in Volt
  * `e3dc_wallbox_power` - Wallbox power in Watt
  * `e3dc_wallbox_voltage` - Wallbox voltage in Volt

## Credits

This configuration Files are based on the work of Community-Contribution: [E3DC in Energy Dashboard](https://community.home-assistant.io/t/e3dc-in-energy-dashboard/379800)
