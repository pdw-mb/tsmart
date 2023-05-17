# Python library for T-Smart smart thermostats

This library provides access to [T-Smart smart thermostats](https://www.tsmart.co.uk/), and supports the [Home Assistant integration](https://github.com/pdw-mb/tsmart_ha) for these devices.

```py
from tsmart import TSmart
import asyncio

async def find_devices():
    devices = await TSmart.async_discover()
    print("Found %d devices" % len(devices))
    for device in devices:
        await device.async_get_status()
        print("Thermostat: %s" % device.name)
        print("Temperature: %.1f°C" % device.temperature)

asyncio.run(find_devices())
```
