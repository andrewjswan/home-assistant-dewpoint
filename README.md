# Dewpoint for Home Assistant

[![hacs_badge](https://img.shields.io/badge/HACS-Custom-blue.svg?logo=HomeAssistantCommunityStore&logoColor=white)](https://github.com/custom-components/hacs)
[![GitHub Workflow Status](https://img.shields.io/github/actions/workflow/status/andrewjswan/home-assistant-dewpoint/validate.yml?logo=github)](https://github.com/andrewjswan/home-assistant-dewpoint/actions)
[![GitHub](https://img.shields.io/github/license/andrewjswan/home-assistant-dewpoint?color=blue)](https://github.com/andrewjswan/home-assistant-dewpoint/blob/master/LICENSE)
[![GitHub release (latest SemVer including pre-releases)](https://img.shields.io/github/v/release/andrewjswan/home-assistant-dewpoint?include_prereleases)](https://github.com/andrewjswan/home-assistant-dewpoint/releases)
[![HA Installs][installs]](https://analytics.home-assistant.io/custom_integrations.json)
[![StandWithUkraine](https://raw.githubusercontent.com/vshymanskyy/StandWithUkraine/main/badges/StandWithUkraine.svg)](https://github.com/vshymanskyy/StandWithUkraine/blob/main/docs/README.md)

## Description

Home Assistant custom component to calculate dew point using temperature and humidity sensors.
Calculated using [psychrolib](https://github.com/psychrometrics/psychrolib).


## Installation

[![hacs_default](https://img.shields.io/badge/HACS-Custom-blue.svg?logo=HomeAssistantCommunityStore&logoColor=white)](https://hacs.xyz/)

This integration is part of the custom [HACS](https://hacs.xyz/) repository.

### Method 1:

[![hacs_custom](https://img.shields.io/badge/HACS-Custom-blue.svg?logo=HomeAssistantCommunityStore&logoColor=white)](https://hacs.xyz/)

1. Visit **HACS** → **Integrations** → **...** (3 dots - upper top corner) → **Custom repositories**
2. Click **Add**
3. Paste `andrewjswan/home-assistant-dewpoint` into the **URL** field
4. Chose `Integration` as a **Category**
5. **home-assistant-dewpoint** will appear in the list of available integrations. Install it normally.

### Method 2: 

[![manual](https://img.shields.io/badge/Manual-blue.svg?logo=HomeAssistantCommunityStore&logoColor=white)](https://github.com/andrewjswan/home-assistant-dewpoint/releases/latest)

1. Manually copy `dewpoint` folder from [latest release](https://github.com/andrewjswan/home-assistant-dewpoint/releases/latest) to `/config/custom_components` folder.
2. Restart **Home Assistant**

## Configuration

### Example configuration.yaml

```yaml
sensor:
  - platform: dewpoint
    sensors:
      dewpoint_outside:
        temperature: sensor.temperature_outside
        rel_hum: sensor.humidity_outside
      dewpoint_office:
        temperature: sensor.temperature_office
        rel_hum: sensor.humidity_office
      ...
```

### Configuration options

Key | Type | Required | Description
-- | -- | -- | --
`sensors` | `list` | `True` | List of dewpoint sensors to generate.

#### Configuration options for `sensors` list

Key | Type | Required | Default | Description
-- | -- | -- | -- | --
`friendly_name` | `string` | `False` | `sensor name` | Custom name for the new sensor entity.
`temperature` | `entity_id` | `True` | `none` | Entity ID to read temperature from. (dry-bulb)
`rel_hum` | `entity_id` | `True` | `none` | Entity ID to read relative humidity from.

***

[installs]: https://img.shields.io/badge/dynamic/json?color=41BDF5&logo=home-assistant&label=integration%20usage&suffix=%20installs&cacheSeconds=15600&url=https://analytics.home-assistant.io/custom_integrations.json&query=$.dewpoint.total
[hasc-install-url]: https://my.home-assistant.io/redirect/hacs_repository/?owner=andrewjswan&repository=home-assistant-dewpoint&category=integration
[hacs-install-image]: https://my.home-assistant.io/badges/hacs_repository.svg
