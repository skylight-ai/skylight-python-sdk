# VMStatusResponse


## Fields

| Field                                            | Type                                             | Required                                         | Description                                      | Example                                          |
| ------------------------------------------------ | ------------------------------------------------ | ------------------------------------------------ | ------------------------------------------------ | ------------------------------------------------ |
| `state`                                          | [models.State](../models/state.md)               | :heavy_check_mark:                               | Current state of the VM                          | running                                          |
| `ip_address`                                     | *OptionalNullable[str]*                          | :heavy_minus_sign:                               | Public IP address of the VM                      |                                                  |
| `launch_time`                                    | *OptionalNullable[str]*                          | :heavy_minus_sign:                               | ISO format timestamp of when the VM was launched |                                                  |