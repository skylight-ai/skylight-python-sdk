<!-- Start SDK Example Usage [usage] -->
```python
# Synchronous Example
import os
from skylight_sdk import Skylight


with Skylight(
    apikey=os.getenv("SKYLIGHT_APIKEY", ""),
) as skylight:

    res = skylight.windows.start()

    # Handle response
    print(res)
```

</br>

The same SDK client can also be used to make asynchronous requests by importing asyncio.

```python
# Asynchronous Example
import asyncio
import os
from skylight_sdk import Skylight

async def main():

    async with Skylight(
        apikey=os.getenv("SKYLIGHT_APIKEY", ""),
    ) as skylight:

        res = await skylight.windows.start_async()

        # Handle response
        print(res)

asyncio.run(main())
```
<!-- End SDK Example Usage [usage] -->