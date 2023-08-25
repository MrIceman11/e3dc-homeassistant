# E3DC to Home Assistant

This is a custom configuration for Home Assistant to read data from an E3DC device via ModBus/TCP.

## Installation

Copy the folder `packages` with it's contents to your Home Assistant server at the same level as the `configuration.yaml` file. 

Be sure that you have activated Modbus in your storage.

## Configuration

Add the following line to your `configuration.yaml` file to make sure, the packages are loaded:

```
homeassistant:
  packages: !include_dir_merge_named packages/
```

Edit the file `packages/e3dc/modbus.yaml` and add your E3DC device IP address.

## Extra Config

If you want to add utility_meter for creating daily/weekly/monthly sensors for better graphs or exporting to prometheus you can add the the file `extras/utility_meter.yaml` into the `packages` folder.

## Usage

Restart Home Assistant and you will find the sensors in the `e3dc` entity. Now you can use them in your automations or add the sensors to your dashboard.
If you added HACS to your Home Assistant, you can also add the card called [Power-Distribution-Card](https://github.com/JonahKr/power-distribution-card)

To add the sensor to your Energy Dashboard use the following Sensors:

<img src="https://github.com/MrIceman11/e3dc-homeassistant/raw/main/examples/Dashboard_Config_2.png"/>

It is normal that some sensors are not available. This is because the E3DC device has not yet sent all the values. This can take up to 2 days.

## Sensors

The following sensors are available:

  * `e3dc_grid_export_power` - Grid Export Power in Watt
  * `e3dc_grid_import_power` - Grid Import Power in Watt
  * `e3dc_battery_charge_power` - Battery Charge Power in Watt
  * `e3dc_battery_discharge_power` - Battery Discharge Power in Watt
  * `e3dc_autarky` - Autarky in % per day
  * `e3dc_external_power` - Power of an additional source in Watt
  * `e3dc_own_consumption` - Own Consumption in % per day
  * `e3dc_emergency_power_state_text` - emergency power state in text

## Credits

This configuration Files are based on the work of Community-Contribution: [E3DC in Energy Dashboard](https://community.home-assistant.io/t/e3dc-in-energy-dashboard/379800)

Thangs to [Roman](https://github.com/Roemer) for Sharing his work.
