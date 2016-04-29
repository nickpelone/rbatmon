#!/usr/bin/ruby
# rbatmon: Returns the percent remaining from UPower DisplayDevice
# A simple example for using ruby-dbus
# Author: Nick Pelone <nick.pelone@gmail.com>

require 'dbus'

# Init a dbus connection
bus = DBus.system_bus

# Connect to the org.freedesktop.UPower dbus service
upower_service = bus["org.freedesktop.UPower"]

# Connect to the composite power display for multiple batteries
upower_device = upower_service.object '/org/freedesktop/UPower/devices/DisplayDevice'

# You need to call this before interfaces to UPower.Device are available
# which contain the actual values you care about
upower_device.introspect

percentage = upower_device["org.freedesktop.UPower.Device"]["Percentage"]

# Cast the percentage to a whole int for nice presentation.
puts percentage.to_i
