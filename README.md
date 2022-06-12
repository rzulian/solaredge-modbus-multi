[![hacs_badge](https://img.shields.io/badge/HACS-Default-41BDF5.svg?style=for-the-badge)](https://github.com/hacs/integration)

# solaredge-modbus-multi
_Note: readme has been updated for version 2.0.0 (currently in pre-release)_

A Home Assistant integration for SolarEdge inverters using Modbus/TCP. It supports single inverters, multiple inverters, meters, batteries, and many other improvements over other integrations that didn't work well with a multi-device setup.

It is designed to communicate locally using Modbus/TCP where you have a single Leader (Master) inverter connected with one or more Follower (Slave) inverters chained using the RS485 bus. Inverters can have up to three meters and two batteries.

### Features
* Inverter support for 1 to 32 SolarEdge inverters.
* Meter support for 1 to 3 meters per inverter.
* Battery support for 1 or 2 batteries per inverter.
* Automatically detects meters and batteries.
* Polling frequency configuration option (10 to 86400 seconds).
* Configurable starting inverter device ID.
* Connects using Modbus/TCP - no cloud dependencies.
* Informational sensor for device and its attributes
* Supports status and error reporting sensors.
* User friendly configuration through Config Flow.

Requires Home Assistant 2022.2.0 and newer.

## Installation
Copy the `solaredge_modbus_multi` folder into to your Home Assistant `config/custom_components` folder,

OR

Install with HACS: Search for "SolarEdge Modbus Multi" in the default repository.

After rebooting Home Assistant, this integration can be configured through the integration setup UI.

### Configuration
[WillCodeForCats/solaredge-modbus-multi/wiki/Configuration](https://github.com/WillCodeForCats/solaredge-modbus-multi/wiki/Configuration)

### Documentation

[WillCodeForCats/solaredge-modbus-multi/wiki](https://github.com/WillCodeForCats/solaredge-modbus-multi/wiki)

### Upgrading from v1.2.x to v2.x.x
1.  Delete integration from Settings -> Devices & Services.
2. Update to 2.x release.
3. Add the integration again.

Fixing #21 causes HA to recreate entities. Updating in place will cause existing entities will be seen as duplicates and HA will suffix them with `_2`. If this happens you can either update everything to use the new names, or follow the update procedure to avoid renaming. This assumes the default entity names; custom names will have to be handled manually in any case.

### Upgrading from v1.1.x to v1.2.x
Follow instructions at: [How To Upgrade from v1.1.x to v1.2.x](https://github.com/WillCodeForCats/solaredge-modbus-multi/wiki/How-To-Upgrade-from-v1.1.x-to-v1.2.x)

## Specifications
- https://www.solaredge.com/sites/default/files/sunspec-implementation-technical-note.pdf
- https://sunspec.org/wp-content/uploads/2015/06/SunSpec-Specification-Common-Models-A12031-1.6.pdf
