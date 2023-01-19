# smartthings-edge-drivers

A very preliminary edge driver for HomeSeer Z-Wave Switches WS100+, WD100+, WD200+, WS200+, WX300, FC200+.
So far, it only includes basic features and multi-click events.
Help wanted!

Channel Invite:
https://bestow-regional.api.smartthings.com/invite/eGM6WwPwP2AP 

After accepting this channel invite and enrolling, any HomeSeer switches you add should automatically be assigned this Device Type Handler (DTH).

To see if a switch is using this device handler, go to Devices, open the switch and click the "..." button. If "Driver" is in the list, then it's using the new Edge DTH code. The driver name will be "HomeSeer Z-Wave Switch" for this DTH. If "Driver" is not present, it's using the legacy Groovy handler. In this case you should remove the device and re-add it.

## Removing the old handler

When removing the device via the SmartThings app, it will prompt you to follow your manufacturer's directions to unpair the old device. For all models the factory reset sequence is:

1) Turn the light on.
2) Quickly tap up 3 times
3) Quickly tap down 3 times

If it worked, it will turn the light off then back on again, and the remove operation will complete successfully in the SmartThings app.

Newer models like WX300 have a dedicated Z-Wave exclusion mode which you should use instead as it doesn't reset the switch wiring mode.

## Assigning multi-tap actions

To react to a multi-tap event, go to Automation and create a Routine. Under "If", choose "Device status", choose the switch and it should show all of the multi-tap events you can react to. Then you can add the result as normal for the routine.
