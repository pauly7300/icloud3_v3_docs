# iCloud3 Version 3.0 Change Log



#### iCloud3 is now a Home Assistant Integration

- Add the iCloud3 Integration and configure all settings on the Devices & Settings > Integration screen
- Update parameters with 10 configuration screens
- Add and configure tracked devices
- No *yaml* parameters, no *config_ic3.yaml*, no platform entries in the HA *configuration.yaml* file
- Select Family Sharing device and Find-my-Friend device providing location data from a list of devices in the iCloud account
- Select the iOS App device to monitor from a list of HA mobile_app device_tracker entities
- The iCloud3 devicename is no longer tied to the iCloud device name (it can be anything you want)
- Actions for tracking control (pause, resume, restart), iCloud operations (Reset iCloud Interface, Enter Verification Code) can be executed
- Parameters are edited and verified while they are entered
- Most parameters are selected from lists
- Restart iCloud3 after the configuration has been changed without restarting Home Assistant



#### Event Log card

- The iCloud3 Event Log card is automatically added or updated to theLovelace Resourcewhenthe Event Log custom card directory is changed. It does not have to be entered manually
- Sensor friendly names are easier to read when setting up new cards
- Reformatted most messages for clarity
- Easier to understand error messages
- Status and alert messages are clearer and provide more information
- Tracking monitor messages show more information
- More details about location data source helps identify relocation request reasons
- The location times from the iOS App and iCloud data is now shows the source of the data and how it is being used

#### Track from more than one zone

- Full tracking (distance, travel time, etc.) can be done for more than one zone
- An alternate ‘home’ zone can be set up if you are away from Home for an extended time (trip, vacation home, parents house, etc.)
- You can turn off tracking from the real Home zone
- Multiple zone tracking is configured for an individual device
- Alternate ‘home’ Zone is config by device or globally
- A device’s sensors show the tracking information for the ‘Tracked From Zone’ when it is close to the zone or the Home zone when further away

#### Starting iCloud3

- Faster Startup - iCloud3 starts up in about 10-seconds once HA loads it
- Startup messages provide more information about tracked devices, available iCloud Family Sharing and Find-my-Friends devices and these that can be monitored using the iOS App
- A connection to iCloud account is started during the initial HA startup Stage before iCloud3 its fully loaded
- Analysis of iCloud location data has been improved, resulting in fewer internet requests and improved response times
- iCloud3 has been rewritten to use the latest Python programming practices and to take advantage of newer Home Assistant support modules
- The state values of all of the sensors are restored when starting instead of being located in the Home zone.

#### Waze History Database

- Results of Waze travel time and distance requests are stored in a local data base for each 10-meter segment of routes traveled. This, over time, greatly reduces the number of internet requests and improved performance
- The saved locations displayed on a Lovelace Map card

#### Other New or Enhanced Features

- Pass through zones -The Zone Enter trigger is delayed for 1-minute in case you are just driving through it

- Tacking Modes have been added for each device:

  - Track - Request the devices location when an update is needed

  - Monitor- Update location when another device requests theirs
  - Inactive - Keep device parameters but do not track it

- Battery Sensors - The device’s battery level is updated every 2-minutes from the iOS App and from iCloud when the location is updated
- Near-by Devices - Tracking results of near-by devices are used, reducing Waze requests and improving performanc

#### Breaking Changes - The following items have been changed or removed

- The *update* Service Call has been renamed to *action*
- Some unused Service Call options have been removed (setting intervals, setting zones, changing Waze operations, etc)
- Near_Zone has been removed

------

Gary Cobb *(aka geekstergary)*

*December, 2022*

