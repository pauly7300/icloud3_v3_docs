------

The *Settings App > General > About* screen on the iPhone and other devices is used to set up the device's name that is used in the Family Sharing List and FindMy App. The iOS App, once installed on the iPhone, will also use this name to create it's device_tracker entity name used by HA and the *mobile_app* integration. Generally, it changes all upper-case letters to lower-case and all spaces to underscores ('Gary iPhone' → 'gary_iphone'). The iOS App may add a suffix number to make this name unique if it is already used.

You will assign an iCloud3 device name (gary_iphone) and a a friendly name (Gary) when you add the device on the *Configurator > iCloud3 Devices* screen. Those values are used to create the device_tracker entity, sensor entity  and the sensor's friendly name:

- device_tracker.gary_iphone
- sensor.gary_iphone_travel_time, sensor.gary_iphone_zone_distance, etc.
- Gary TravelTime, Gary ZoneDistance, etc.

Note: Additional sensors are created when you are tracking from an additional zone. This is discussed in Chapter # - Sensors.

### Tracking from More than One Zone

Normally, you will only be tracking a device from the Home Zone. The sensor entities related to travel time, distance, intervals, next update time, etc. are all for the Home Zone. However, if you are tracking a device from more than one zone, you will select the other zone(s) on the *iCloud3 Devices* screen (*Track from Zone* parameter). Sensors are created for the Home Zone and for the additional zone(s) with the zone name added to the end of the entity name:

- sensor.gary_iphone_travel_home, sensor.gary_iphone_zone_distance_home, etc.
- Gary TravelTime (Home), Gary ZoneDistance (Home), etc.
- sensor.gary_iphone_travel_time_warehouse, sensor.gary_iphone_zone_distance_warehouse. etc.
- Gary TravelTime (Warehouse), Gary ZoneDistance (Warehouse), etc.

The sensors previously created (sensor.gary_iphone_travel_time, sensor.gary_iphone_zone_distance, etc.) are still created, however their meaning changes. They now contain the results of the closest zone you are traveling towards. If you are closer to the Warehouse Zone, it reports the Warehouse Zone values, if closer to Home, the Home values are reported. When the closer zone is the other zone, it's first letter is displayed in a circle in the 'zone_distance' sensor.

