# PackageInstallResponse


## Fields

| Field                                             | Type                                              | Required                                          | Description                                       | Example                                           |
| ------------------------------------------------- | ------------------------------------------------- | ------------------------------------------------- | ------------------------------------------------- | ------------------------------------------------- |
| `status`                                          | *str*                                             | :heavy_check_mark:                                | Status of the package installation                | success                                           |
| `message`                                         | *str*                                             | :heavy_check_mark:                                | Human-readable status message                     | Packages installation initiated                   |
| `command_id`                                      | *OptionalNullable[str]*                           | :heavy_minus_sign:                                | Command ID for tracking the installation progress |                                                   |