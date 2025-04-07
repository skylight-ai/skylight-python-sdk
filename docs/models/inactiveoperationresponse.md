# InactiveOperationResponse


## Fields

| Field                                                            | Type                                                             | Required                                                         | Description                                                      | Example                                                          |
| ---------------------------------------------------------------- | ---------------------------------------------------------------- | ---------------------------------------------------------------- | ---------------------------------------------------------------- | ---------------------------------------------------------------- |
| `status`                                                         | *str*                                                            | :heavy_check_mark:                                               | Status of the operation                                          | success                                                          |
| `message`                                                        | *str*                                                            | :heavy_check_mark:                                               | Human-readable status message                                    | Operation completed successfully                                 |
| `state`                                                          | *str*                                                            | :heavy_check_mark:                                               | State of the instance (running, pending, hibernated, terminated) | running                                                          |