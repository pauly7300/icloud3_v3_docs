------

iCloud3 uses location data from the Apple iCloud account and the Home Assistant Companion App that can be installed on your iPhone or iPad. 



### iCloud Account

iCloud Location Service provides location information for all devices (iPhone, iPad, etc) using two methods:

- The family members in the Family Sharing List on the iCloud account (*Family Sharing* or *FamShr*). The location of all devices on the list is returned when a request is made. 
- The people (friends) that have shared their location with you on the FindMy app (*Find-my-Friends* or *FmF*). The email address or phone number of the friend identifies the device. 

The FamShr method is always used since the iCloud Account owner is part of the Family Sharing List. The Find-my-Friends method is only used to locate devices not on the list. 



### Home Assistant Companion iOS App (iOS App)

The iOS App can be installed on iPhones and iPads to monitor the device's location and provide zone enter/exit triggers. It will:

- Issue a Zone Enter/Exit trigger when it enters or exits a zone - This trigger is immediately received by iCloud3, analyzed and will update the device's location if the trigger is accurate.
- Update the device's location -  iCloud3 monitors the iOS App location data and updates the tracking information.



### HA Proximity Component

!> Do not use the HA proximity component

It can report old location information that causes GPS wandering and incorrect locations.  iCloud3 duplicates the proximity functions and discards poor location information.  You also do not need OwnTracks or other location based trackers or Nmap, netgear, ping or other network monitors.

