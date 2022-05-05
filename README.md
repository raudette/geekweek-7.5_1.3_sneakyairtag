# SneakyAirTag

SneakyAirTag tries to increase the stealthyness of Positive Security's Find-You tag, found here:
https://github.com/positive-security/find-you

Which itself was built on the excellent work of:
https://github.com/seemoo-lab/openhaystack

It tries to improve the stealthyness as follows:
- Rotates keys on a random interval, between 30 and 60 seconds (Find-You rotates every 30 seconds)
- Transmits at random power levels, in an attempt to avoid detection based on a consistent signal strength.  

In our testing, even with these changes, we were still able to identify stealth tags in an area with other Apple Find My devices.  Even at the ESP32's lowest power level, the stealth tracker can be identified as the signal strength of the stealth tracker is higher than other devices the viscinity of the tracked subject.

# Build and Deploy

In the OpenHaystack application, generate keys.  Copy the advertising key as a byte array, and paste into the public_keys variable in openhaystack_main.c.

Build and flash the ESP32 as per the instructions in ESP32/README.md