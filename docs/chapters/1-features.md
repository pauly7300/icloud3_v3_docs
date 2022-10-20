------

iCloud3 is a device tracker custom component that tracks your iPhones, iPads, Apple Watches, AirPods and other Apple devices. It requests location data from Apple's iCloud  Location Services and monitors various triggers sent from the Home Assistant Companion App (iOS App) to Home Assistant. Sensors are updated with the device's location, distance from zones, travel time to zones, etc. 

Although Home Assistant has it's own official iCloud component, iCloud3 goes far beyond it's capabilities. The important highlights include:

- Track devices from several sources - The Family Sharing list, the FindMy App and the HA Companion App (iOS App ).
- Actively track a device - Request it's location on a regular interval.
- Passively monitor a device - Do not request it's location, just report it when it is available after a tracked device location request.
- Waze Route Service - Request the travel time and distance to a zone from the current location. 
- Waze Route Service History Database - Save Waze travel time information to a local database. 
- Track from Multiple Zones - The device is always tracked from the Home Zone. Now it can also be tracked from another zone (office, second home, parents, etc.) and trigger automations based on that zone. 
- Improved GPS Accuracy - GPS wandering errors leading to incorrect zone exits are eliminated.
- Stationary Zone - Creates a dynamic *Stationary Zone* by monitoring when the device has not moved for a while (doctors office, store, friend's house) that conserves battery life.
- Sensors and more sensors - Many sensors are created and updated with distance, travel time, polling data, battery status,  zone attributes, etc. 
- Event Log - Display the current status and event history of every tracked and monitored device,
- Detailed debugging information - Several levels location history transactions can be displayed in the Event Log or the Home Assistant Log File.
- HA Integration - iCloud3 is added as an integration on the *HA Settings > Devices & Services > Integrations* screen.
- *The Configurator* - All of the parameters are updated on configuration screens selected from the *iCloud3 Integrations* entry.
- Updating and Restarting - iCloud3 can be restarted without restarting Home Assistant. The current device_tracker and sensor entity states are restored on a restart.
- Device_tracker and sensor entities - iCloud3 devices and sensors are true Home Assistant entities. They are added, deleted and updated using *The Configurator*, not the HA Devices and Entities screens.
- Nearby Devices - The location's of all devices is monitored to see if there are any in the same location.



------

## The iCloud Account and the iOS App

iCloud3 uses location data from the Apple iCloud account and the iOS App if it is installed on the device. 



#### iCloud Account

iCloud Location Service provides location information for all devices (iPhone, iPad, etc) using two methods:

- The family members in the Family Sharing List on the iCloud account (*Family Sharing* or *FamShr*). The location of all devices on the list is returned when a request is made. 
- The people (friends) that have shared their location with you on the FindMy app (*Find-my-Friends* or *FmF*). The email address or phone number of the friend identifies the device. 

The FamShr method is always used since the iCloud Account owner is part of the Family Sharing List. The Find-my-Friends method is only used to locate devices not on the list. 



#### Home Assistant Companion iOS App (iOS App)

The iOS App can be installed on iPhones and iPads to monitor the device's location and provide zone enter/exit triggers. It will:

- Issue a Zone Enter/Exit trigger when it enters or exits a zone - This trigger is immediately received by iCloud3, analyzed and will update the device's location if the trigger is accurate.
- Update the device's location -  iCloud3 monitors the iOS App location data and updates the tracking information.



#### HA Proximity Component

Do not use the HA proximity component - It can report old location information that causes GPS wandering and incorrect locations.  iCloud3 duplicates the proximity functions and discards poor location information.  You also do not need OwnTracks or other location based trackers or Nmap, netgear, ping or other network monitors.

