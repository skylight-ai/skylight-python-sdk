# Interact
(*interact*)

## Overview

### Available Operations

* [click](#click) - Click
* [drag](#drag) - Drag
* [screenshot](#screenshot) - Take Screenshot
* [move](#move) - Move Mouse
* [keypress](#keypress) - Keypress
* [type](#type) - Type Text
* [scroll](#scroll) - Scroll
* [get_file](#get_file) - Get File

## click

Perform a click operation at the specified coordinates or current position

- If x and y are provided, click at those coordinates
- If x and y are omitted, click at the current cursor position
- Use button="left", clicks=1 for a single left click
- Use button="right", clicks=1 for a right click
- Use button="middle", clicks=1 for a middle click
- Use button="left", clicks=2 for a double click

Requires API key authentication.

### Example Usage

```python
import os
from skylight_sdk import Skylight


with Skylight(
    server_url="https://api.example.com",
    apikey=os.getenv("SKYLIGHT_APIKEY", ""),
) as skylight:

    res = skylight.interact.click(instance_id="<id>", x=100, y=200, interval=0)

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `instance_id`                                                       | *str*                                                               | :heavy_check_mark:                                                  | N/A                                                                 |
| `x`                                                                 | *OptionalNullable[int]*                                             | :heavy_minus_sign:                                                  | N/A                                                                 |
| `y`                                                                 | *OptionalNullable[int]*                                             | :heavy_minus_sign:                                                  | N/A                                                                 |
| `button`                                                            | [Optional[models.Button]](../../models/button.md)                   | :heavy_minus_sign:                                                  | N/A                                                                 |
| `clicks`                                                            | *Optional[int]*                                                     | :heavy_minus_sign:                                                  | N/A                                                                 |
| `interval`                                                          | *OptionalNullable[float]*                                           | :heavy_minus_sign:                                                  | N/A                                                                 |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.StandardResponse](../../models/standardresponse.md)**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| models.ErrorResponse       | 403, 404                   | application/json           |
| models.HTTPValidationError | 422                        | application/json           |
| models.ErrorResponse       | 500                        | application/json           |
| models.APIError            | 4XX, 5XX                   | \*/\*                      |

## drag

Perform a drag operation along a path of coordinates

- path: List of points to drag through, each with 'x' and 'y' coordinates
- button: Mouse button to use for dragging (default: "left")

Requires API key authentication.

### Example Usage

```python
import os
from skylight_sdk import Skylight


with Skylight(
    server_url="https://api.example.com",
    apikey=os.getenv("SKYLIGHT_APIKEY", ""),
) as skylight:

    res = skylight.interact.drag(instance_id="<id>", path=[
        {
            "x": 100,
            "y": 200,
        },
        {
            "x": 200,
            "y": 300,
        },
        {
            "x": 300,
            "y": 400,
        },
    ], step=5)

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                            | Type                                                                                 | Required                                                                             | Description                                                                          |
| ------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------ |
| `instance_id`                                                                        | *str*                                                                                | :heavy_check_mark:                                                                   | N/A                                                                                  |
| `path`                                                                               | List[Dict[str, *int*]]                                                               | :heavy_check_mark:                                                                   | N/A                                                                                  |
| `button`                                                                             | [Optional[models.DragRequestButton]](../../models/dragrequestbutton.md)              | :heavy_minus_sign:                                                                   | N/A                                                                                  |
| `step`                                                                               | *OptionalNullable[int]*                                                              | :heavy_minus_sign:                                                                   | Optional step size for drag movements. If not provided, movement will be continuous. |
| `retries`                                                                            | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                     | :heavy_minus_sign:                                                                   | Configuration to override the default retry behavior of the client.                  |

### Response

**[models.StandardResponse](../../models/standardresponse.md)**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| models.ErrorResponse       | 403, 404                   | application/json           |
| models.HTTPValidationError | 422                        | application/json           |
| models.ErrorResponse       | 500                        | application/json           |
| models.APIError            | 4XX, 5XX                   | \*/\*                      |

## screenshot

Take a screenshot of the VM

Requires API key authentication.

### Example Usage

```python
import os
from skylight_sdk import Skylight


with Skylight(
    server_url="https://api.example.com",
    apikey=os.getenv("SKYLIGHT_APIKEY", ""),
) as skylight:

    res = skylight.interact.screenshot(instance_id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `instance_id`                                                       | *str*                                                               | :heavy_check_mark:                                                  | N/A                                                                 |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[Any](../../models/.md)**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| models.ErrorResponse       | 403, 404                   | application/json           |
| models.HTTPValidationError | 422                        | application/json           |
| models.ErrorResponse       | 500                        | application/json           |
| models.APIError            | 4XX, 5XX                   | \*/\*                      |

## move

Move the mouse to the specified coordinates

Requires API key authentication.

### Example Usage

```python
import os
from skylight_sdk import Skylight


with Skylight(
    server_url="https://api.example.com",
    apikey=os.getenv("SKYLIGHT_APIKEY", ""),
) as skylight:

    res = skylight.interact.move(instance_id="<id>", x=100, y=200)

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `instance_id`                                                       | *str*                                                               | :heavy_check_mark:                                                  | N/A                                                                 |
| `x`                                                                 | *int*                                                               | :heavy_check_mark:                                                  | N/A                                                                 |
| `y`                                                                 | *int*                                                               | :heavy_check_mark:                                                  | N/A                                                                 |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.StandardResponse](../../models/standardresponse.md)**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| models.ErrorResponse       | 403, 404                   | application/json           |
| models.HTTPValidationError | 422                        | application/json           |
| models.ErrorResponse       | 500                        | application/json           |
| models.APIError            | 4XX, 5XX                   | \*/\*                      |

## keypress

Press the specified keys simultaneously (e.g. ['ctrl', 'alt', 'delete'])

Requires API key authentication.

### Example Usage

```python
import os
from skylight_sdk import Skylight


with Skylight(
    server_url="https://api.example.com",
    apikey=os.getenv("SKYLIGHT_APIKEY", ""),
) as skylight:

    res = skylight.interact.keypress(instance_id="<id>", keys=[
        "super",
        "shift",
        "s",
    ])

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `instance_id`                                                       | *str*                                                               | :heavy_check_mark:                                                  | N/A                                                                 |
| `keys`                                                              | List[*str*]                                                         | :heavy_check_mark:                                                  | N/A                                                                 |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.StandardResponse](../../models/standardresponse.md)**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| models.ErrorResponse       | 403, 404                   | application/json           |
| models.HTTPValidationError | 422                        | application/json           |
| models.ErrorResponse       | 500                        | application/json           |
| models.APIError            | 4XX, 5XX                   | \*/\*                      |

## type

Type the specified text with optional delay between keystrokes

Requires API key authentication.

### Example Usage

```python
import os
from skylight_sdk import Skylight


with Skylight(
    server_url="https://api.example.com",
    apikey=os.getenv("SKYLIGHT_APIKEY", ""),
) as skylight:

    res = skylight.interact.type(instance_id="<id>", text="Hello, world!", interval=0.05)

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `instance_id`                                                       | *str*                                                               | :heavy_check_mark:                                                  | N/A                                                                 |
| `text`                                                              | *str*                                                               | :heavy_check_mark:                                                  | N/A                                                                 |
| `interval`                                                          | *OptionalNullable[float]*                                           | :heavy_minus_sign:                                                  | N/A                                                                 |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.StandardResponse](../../models/standardresponse.md)**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| models.ErrorResponse       | 403, 404                   | application/json           |
| models.HTTPValidationError | 422                        | application/json           |
| models.ErrorResponse       | 500                        | application/json           |
| models.APIError            | 4XX, 5XX                   | \*/\*                      |

## scroll

Scroll at the specified coordinates

Requires API key authentication.

### Example Usage

```python
import os
from skylight_sdk import Skylight


with Skylight(
    server_url="https://api.example.com",
    apikey=os.getenv("SKYLIGHT_APIKEY", ""),
) as skylight:

    res = skylight.interact.scroll(instance_id="<id>", x=100, y=200, step=20)

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                              | Type                                                                                   | Required                                                                               | Description                                                                            |
| -------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------- |
| `instance_id`                                                                          | *str*                                                                                  | :heavy_check_mark:                                                                     | N/A                                                                                    |
| `x`                                                                                    | *int*                                                                                  | :heavy_check_mark:                                                                     | N/A                                                                                    |
| `y`                                                                                    | *int*                                                                                  | :heavy_check_mark:                                                                     | N/A                                                                                    |
| `scroll_x`                                                                             | *Optional[int]*                                                                        | :heavy_minus_sign:                                                                     | Horizontal scroll amount                                                               |
| `scroll_y`                                                                             | *Optional[int]*                                                                        | :heavy_minus_sign:                                                                     | Vertical scroll amount                                                                 |
| `step`                                                                                 | *OptionalNullable[int]*                                                                | :heavy_minus_sign:                                                                     | Optional step size for scroll movements. If not provided, movement will be continuous. |
| `retries`                                                                              | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                       | :heavy_minus_sign:                                                                     | Configuration to override the default retry behavior of the client.                    |

### Response

**[models.StandardResponse](../../models/standardresponse.md)**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| models.ErrorResponse       | 403, 404                   | application/json           |
| models.HTTPValidationError | 422                        | application/json           |
| models.ErrorResponse       | 500                        | application/json           |
| models.APIError            | 4XX, 5XX                   | \*/\*                      |

## get_file

Get a secure download link for a file on the VM

Generates a presigned S3 URL for the client to download the file directly

Requires API key authentication.

### Example Usage

```python
import os
from skylight_sdk import Skylight


with Skylight(
    server_url="https://api.example.com",
    apikey=os.getenv("SKYLIGHT_APIKEY", ""),
) as skylight:

    res = skylight.interact.get_file(instance_id="<id>", request_body={
        "key": "<value>",
    })

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `instance_id`                                                       | *str*                                                               | :heavy_check_mark:                                                  | N/A                                                                 |
| `request_body`                                                      | Dict[str, *str*]                                                    | :heavy_check_mark:                                                  | N/A                                                                 |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.GetFileResponse200GetFile](../../models/getfileresponse200getfile.md)**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| models.ErrorResponse       | 403, 404                   | application/json           |
| models.HTTPValidationError | 422                        | application/json           |
| models.ErrorResponse       | 500                        | application/json           |
| models.APIError            | 4XX, 5XX                   | \*/\*                      |