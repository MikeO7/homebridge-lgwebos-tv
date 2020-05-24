<p align="center">
  <a href="https://github.com/grzegorz914/homebridge-lgwebos-tv"><img src="https://raw.githubusercontent.com/grzegorz914/homebridge-lgwebos-tv/master/graphics/lgwebos.png" height="140"></a>
</p>

<span align="center">

# Homebridge LG webOS TV
[![verified-by-homebridge](https://badgen.net/badge/homebridge/verified/purple)](https://github.com/homebridge/homebridge/wiki/Verified-Plugins)
[![npm](https://badgen.net/npm/dt/homebridge-lgwebos-tv?color=purple)](https://www.npmjs.com/package/homebridge-lgwebos-tv) [![npm](https://badgen.net/npm/v/homebridge-lgwebos-tv?color=purple)](https://www.npmjs.com/package/homebridge-lgwebos-tv) [![GitHub pull requests](https://img.shields.io/github/issues-pr/grzegorz914/homebridge-lgwebos-tv.svg)](https://github.com/grzegorz914/homebridge-lgwebos-tv/pulls)
[![GitHub issues](https://img.shields.io/github/issues/grzegorz914/homebridge-lgwebos-tv.svg)](https://github.com/grzegorz914/homebridge-lgwebos-tv/issues)

Homebridge plugin to control LG webOS TV in HomeKit as TV service. Tested with LGOLED65G6V, 32LM6300PLA, LG49SK8500.

</span>

## Info
1. Power ON/OFF short press tile in HomeKit app.
2. RC/Media control is possible after You go to the RC app on iPhone/iPad.
3. Speaker control is possible after You go to RC app on iPhone/iPad `Speaker Service`.
4. Legacy volume and mute control is possible throught extra `lightbulb` (slider) or using Siri `Volume Service`.
5. Inputs can be changed after loong press tile in HomeKit app and select from the list.
6. Siri control.


<p align="left">
  <a href="https://github.com/grzegorz914/homebridge-lgwebos-tv"><img src="https://raw.githubusercontent.com/grzegorz914/homebridge-lgwebos-tv/master/graphics/homekit.png" height="300"></a>  <a href="https://github.com/grzegorz914/homebridge-lgwebos-tv"><img src="https://raw.githubusercontent.com/grzegorz914/homebridge-lgwebos-tv/master/graphics/inputs.png" height="300"></a>  <a href="https://github.com/grzegorz914/homebridge-lgwebos-tv"><img src="https://raw.githubusercontent.com/grzegorz914/homebridge-lgwebos-tv/master/graphics/RC.png" height="300"></a>
</p>

## Limitations
Due to HomeKit app limitation max. services for 1 accessory is 100. Over this value HomeKit app will no response. As services in this accessory are, (1.information service, 2.speaker service, 3.lightbulb service, 4.television service and inputs service 5-100(where every input = 1 service)). If all services are enabled possible inputs to use is 96.

## Package
1. [Homebridge](https://github.com/homebridge/homebridge)
2. [Homebridge Config UI X](https://github.com/oznu/homebridge-config-ui-x)

## Installation
1. Follow the step-by-step instructions on the [Homebridge Wiki](https://github.com/homebridge/homebridge/wiki) for how to install Homebridge.
2. Follow the step-by-step instructions on the [Homebridge Config UI X](https://github.com/oznu/homebridge-config-ui-x/wiki) for how to install Homebridge Config UI X.
3. Install homebridge-lgwebos-tv using: `npm install -g homebridge-lgwebos-tv` or search for `Lgwebos TV` in Config UI X.

## Configuration TV
1. [Please configure LG Connect Apps](https://www.lg.com/ca_en/support/product-help/CT20098005-1437129879355-others)

## Configuration plugin
1. Use [Homebridge Config UI X](https://github.com/oznu/homebridge-config-ui-x) to configure the plugin (strongly recomended), or update your configuration file manually. See `sample-config.json` in this repository for a sample or add the bottom example to Your config.json file.
2. All inputs reference and name can be found in: `homebridge_directory/lgwebosTv/apps_19216818` where `name == title` and `reference == id`
3. In `volumeControl` You can select what a additional volume control type You want to use (None, Slider, Fan). This not working with HDMI ARC control.
4. If `switchInfoMenu` is enabled, `I` button change its behaviour in RC app between Menu and INFO.
5. If `supportOldWebOs` is enable, U can use old webOS TV =< 2.0.

<p align="left">
  <a href="https://github.com/grzegorz914/homebridge-lgwebos-tv"><img src="https://raw.githubusercontent.com/grzegorz914/homebridge-lgwebos-tv/master/graphics/ustawienia.png" height="150"></a>
</p>

```json
{
    "platform": "LgWebOsTv",
    "devices": [
        {
            "name": "LG TV",
            "host": "192.168.1.8",
            "mac": "ab:cd:ef:fe:dc:ba",
            "volumeControl": 0,
            "switchInfoMenu": false,
            "supportOldWebOs": false,
            "inputs": [
                   {
                            "name": "Live TV",
                            "reference": "com.webos.app.livetv",
                            "type": "TUNER"
                  },
                  {
                            "name": "HDMI 1",
                            "reference": "com.webos.app.hdmi1",
                            "type": "HDMI"
                 },
                 {
                            "name": "HDMI 2",
                            "reference": "com.webos.app.hdmi2",
                            "type": "HDMI"
                },
                {
                    "name": "HDMI 3",
                    "reference": "com.webos.app.hdmi3",
                     "type": "HDMI"
                },
                {
                    "name": "HDMI 4",
                    "reference": "com.webos.app.hdmi4",
                     "type": "HDMI"
                },
                {
                    "name": "Netflix",
                    "reference": "netflix",
                     "type": "APPLICATION"
                },
                {
                    "name": "YouTube",
                    "reference": "youtube.leanback.v4",
                     "type": "APPLICATION"
                },
                {
                    "name": "LG Store",
                    "reference": "com.webos.app.discovery",
                     "type": "APPLICATION"
                }
            ]
        }
    ]
}
```
## Whats new:
https://github.com/grzegorz914/homebridge-lgwebos-tv/blob/master/CHANGELOG.md
