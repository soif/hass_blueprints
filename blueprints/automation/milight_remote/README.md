# Milight Remote

Allows control of up to 8 (preferably RGB) lights using an affordable yet convenient [Milight Remote](https://www.aliexpress.com/w/wholesale-milight-remote.html).

### Requirements

- Milight remote.
- Milight Hub, built from the excellent [Esp8266_Milight_Hub Project](https://github.com/sidoh/esp8266_milight_hub).
- RGB Lights.


### Installation

Click the following button:

[![Open your Home Assistant instance and show the blueprint import dialog with a specific blueprint pre-filled.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https%3A%2F%2Fraw.githubusercontent.com%2Fsoif%2Fhass_blueprints%2Frefs%2Fheads%2Fmaster%2Fblueprints%2Fautomation%2Fmilight_remote%2Fmilight_remote.yaml)

### Configuration

 Milight remotes publish commands to an MQTT topic with the following default format: 
`milight/state/DEVICE_ID/DEVICE_TYPE/GROUP_ID`

To configure your automation, you'll need to provide the `DEVICE_ID` and `DEVICE_TYPE`. These can be found in the Milight Hub web interface on the 'Sniffer' page. Press any button on the remote to see them appear in the list..

- `DEVICE_ID` : Use the hexadecimal value with a "0x" prefix. For example, if you see "6639" (decimal) in the Sniffer page, [convert it](https://www.binaryhexconverter.com/decimal-to-hex-converter) to "0x19EF" (hexadecimal).

- `DEVICE_TYPE` : This depends on your Milight remote model. For the B05 remote, it is `rgb_cct`.

`GROUP_ID` Corresponds to the 'group' buttons on the remote. Group 0 is the master, followed by buttons 1 to 4 or 1 to 8, depending on your remote model.

Specify which entity or entities will be controlled by each button group. 

### Supported features
- On/OFF buttons
- Brightness slider
- Color slider
- White button

### Unsupported features
- mode button
- Speed Up/Down buttons
