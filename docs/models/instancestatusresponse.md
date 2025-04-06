# InstanceStatusResponse


## Fields

| Field                             | Type                              | Required                          | Description                       | Example                           |
| --------------------------------- | --------------------------------- | --------------------------------- | --------------------------------- | --------------------------------- |
| `instance_id`                     | *str*                             | :heavy_check_mark:                | N/A                               |                                   |
| `state`                           | *str*                             | :heavy_check_mark:                | Current state of the instance     | running                           |
| `knowledge`                       | *str*                             | :heavy_check_mark:                | Current knowledge of the instance | unknown                           |
| `livestream_url`                  | *str*                             | :heavy_check_mark:                | URL to livestream the instance    | launchskylight.com/embed/i-123456 |
| `assigned_at`                     | *OptionalNullable[str]*           | :heavy_minus_sign:                | When the instance was assigned    | 2023-01-01T12:00:00Z              |