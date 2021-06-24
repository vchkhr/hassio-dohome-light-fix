# Home Assistant DoHome Light Fix
Fixes light bulbs in DoHome component for Home Assistant.

## How to Install
1. Install the [DoHome component](https://github.com/SmartArduino/DoHome) for Home Assistant.
2. Replace the `light.py` file with the file from this repository.
3. Restart Home Assistant server.

## List of fixes
- Maximum brightness of white light. \
The original component allows you to set the maximum brightness only up to 20% due to incorrect transmission of the value to the light bulb.
- Transition between white and colored light. \
Now when you set the brightness to more than 99%, only the white LED in the bulb works, while the 3 color LEDs are off (previously they worked, but had no efficiency at all). \
When the brightness value is set from 1 to 99% and the color is selected, colored LEDs work to set the required lighting color, and a white LED to set the required brightness level. \
When the brightness is set to 0% and the color is selected, only the colored LEDs work, getting the maximum output of the desired light, while the white LED is off.
- Reduced the transition time between the states of the light bulb. \
With the previous value, the transition time (turning on, turning off, changing the colors of the deodes and the brightness of white) took too long and caused discomfort. The transition now takes less time.

## Feedback and Donations
Feedback is always welcome at [GitHub Issues](https://github.com/vchkhr/hassio-dohome-light-fix/issues). \
You can donate to this project using [Patreon](https://patreon.com/vchkhr).
