# Interact

## Overview

### Available Operations

* [click](#click) - Click
* [drag](#drag) - Drag
* [screenshot](#screenshot) - Take Screenshot
* [move](#move) - Move Mouse
* [keypress](#keypress) - Keypress
* [type](#type) - Type Text
* [scroll](#scroll) - Scroll
* [install](#install) - Install Applications

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

<!-- UsageSnippet language="python" operationID="click" method="post" path="/interact/click/{instance_id}" -->
```python
import os
import skylight_sdk
from skylight_sdk import Skylight


with Skylight(
    apikey=os.getenv("SKYLIGHT_APIKEY", ""),
) as skylight:

    res = skylight.interact.click(instance_id="<id>", x=100, y=200, button=skylight_sdk.Button.LEFT, clicks=1)

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
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.StandardResponse](../../models/standardresponse.md)**

### Errors

| Error Type                         | Status Code                        | Content Type                       |
| ---------------------------------- | ---------------------------------- | ---------------------------------- |
| models.ForbiddenErrorResponse      | 403                                | application/json                   |
| models.HTTPValidationError         | 422                                | application/json                   |
| models.InteractModelsErrorResponse | 500                                | application/json                   |
| models.APIError                    | 4XX, 5XX                           | \*/\*                              |

## drag

Perform a drag operation along a path of coordinates

- path: List of points to drag through, each with 'x' and 'y' coordinates
- button: Mouse button to use for dragging (default: "left")

Requires API key authentication.

### Example Usage

<!-- UsageSnippet language="python" operationID="drag" method="post" path="/interact/drag/{instance_id}" -->
```python
import os
import skylight_sdk
from skylight_sdk import Skylight


with Skylight(
    apikey=os.getenv("SKYLIGHT_APIKEY", ""),
) as skylight:

    res = skylight.interact.drag(instance_id="<id>", path=[
        {
            "x": 100,
            "y": 200,
        },
    ], button=skylight_sdk.DragRequestButton.LEFT, step=5)

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

| Error Type                         | Status Code                        | Content Type                       |
| ---------------------------------- | ---------------------------------- | ---------------------------------- |
| models.ForbiddenErrorResponse      | 403                                | application/json                   |
| models.HTTPValidationError         | 422                                | application/json                   |
| models.InteractModelsErrorResponse | 500                                | application/json                   |
| models.APIError                    | 4XX, 5XX                           | \*/\*                              |

## screenshot

Take a screenshot of the instance

Requires API key authentication.

### Example Usage

<!-- UsageSnippet language="python" operationID="screenshot" method="post" path="/interact/screenshot/{instance_id}" -->
```python
import os
from skylight_sdk import Skylight


with Skylight(
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

**[models.ScreenshotResponse](../../models/screenshotresponse.md)**

### Errors

| Error Type                         | Status Code                        | Content Type                       |
| ---------------------------------- | ---------------------------------- | ---------------------------------- |
| models.ForbiddenErrorResponse      | 403                                | application/json                   |
| models.HTTPValidationError         | 422                                | application/json                   |
| models.InteractModelsErrorResponse | 500                                | application/json                   |
| models.APIError                    | 4XX, 5XX                           | \*/\*                              |

## move

Move the mouse to the specified coordinates

Requires API key authentication.

### Example Usage

<!-- UsageSnippet language="python" operationID="move" method="post" path="/interact/move/{instance_id}" -->
```python
import os
from skylight_sdk import Skylight


with Skylight(
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

| Error Type                         | Status Code                        | Content Type                       |
| ---------------------------------- | ---------------------------------- | ---------------------------------- |
| models.ForbiddenErrorResponse      | 403                                | application/json                   |
| models.HTTPValidationError         | 422                                | application/json                   |
| models.InteractModelsErrorResponse | 500                                | application/json                   |
| models.APIError                    | 4XX, 5XX                           | \*/\*                              |

## keypress

Press the specified keys simultaneously (e.g. ['ctrl', 'alt', 'delete'])

Requires API key authentication.

### Example Usage

<!-- UsageSnippet language="python" operationID="keypress" method="post" path="/interact/keypress/{instance_id}" -->
```python
import os
from skylight_sdk import Skylight


with Skylight(
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

| Error Type                         | Status Code                        | Content Type                       |
| ---------------------------------- | ---------------------------------- | ---------------------------------- |
| models.InteractModelsErrorResponse | 400                                | application/json                   |
| models.ForbiddenErrorResponse      | 403                                | application/json                   |
| models.HTTPValidationError         | 422                                | application/json                   |
| models.InteractModelsErrorResponse | 500                                | application/json                   |
| models.APIError                    | 4XX, 5XX                           | \*/\*                              |

## type

Type the specified text with optional delay between keystrokes

Requires API key authentication.

### Example Usage

<!-- UsageSnippet language="python" operationID="type" method="post" path="/interact/type/{instance_id}" -->
```python
import os
from skylight_sdk import Skylight


with Skylight(
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

| Error Type                         | Status Code                        | Content Type                       |
| ---------------------------------- | ---------------------------------- | ---------------------------------- |
| models.ForbiddenErrorResponse      | 403                                | application/json                   |
| models.HTTPValidationError         | 422                                | application/json                   |
| models.InteractModelsErrorResponse | 500                                | application/json                   |
| models.APIError                    | 4XX, 5XX                           | \*/\*                              |

## scroll

Scroll at the specified coordinates

Requires API key authentication.

### Example Usage

<!-- UsageSnippet language="python" operationID="scroll" method="post" path="/interact/scroll/{instance_id}" -->
```python
import os
from skylight_sdk import Skylight


with Skylight(
    apikey=os.getenv("SKYLIGHT_APIKEY", ""),
) as skylight:

    res = skylight.interact.scroll(instance_id="<id>", x=100, y=200, scroll_x=0, scroll_y=100, step=20)

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

| Error Type                         | Status Code                        | Content Type                       |
| ---------------------------------- | ---------------------------------- | ---------------------------------- |
| models.ForbiddenErrorResponse      | 403                                | application/json                   |
| models.HTTPValidationError         | 422                                | application/json                   |
| models.InteractModelsErrorResponse | 500                                | application/json                   |
| models.APIError                    | 4XX, 5XX                           | \*/\*                              |

## install

Install Chocolatey packages on a Windows instance. Find a list of packages here: https://community.chocolatey.org/packages.

Requires API key authentication.

### Example Usage

<!-- UsageSnippet language="python" operationID="install" method="post" path="/interact/install/{instance_id}" -->
```python
import os
from skylight_sdk import Skylight


with Skylight(
    apikey=os.getenv("SKYLIGHT_APIKEY", ""),
) as skylight:

    res = skylight.interact.install(instance_id="<id>", packages=[
        "<value 1>",
    ])

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `instance_id`                                                       | *str*                                                               | :heavy_check_mark:                                                  | N/A                                                                 |
| `packages`                                                          | List[*str*]                                                         | :heavy_check_mark:                                                  | List of Chocolatey package names to install                         |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.PackageInstallResponse](../../models/packageinstallresponse.md)**

### Errors

| Error Type                         | Status Code                        | Content Type                       |
| ---------------------------------- | ---------------------------------- | ---------------------------------- |
| models.ForbiddenErrorResponse      | 403                                | application/json                   |
| models.HTTPValidationError         | 422                                | application/json                   |
| models.InteractModelsErrorResponse | 500                                | application/json                   |
| models.APIError                    | 4XX, 5XX                           | \*/\*                              |