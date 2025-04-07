# Windows
(*windows*)

## Overview

### Available Operations

* [start](#start) - Start Instance
* [pause](#pause) - Pause Instance
* [resume](#resume) - Resume Instance
* [terminate](#terminate) - Terminate Instance
* [state](#state) - Get Instance State
* [instances](#instances) - Get All Instances

## start

Start a new Windows  instance.

- timeout_minutes: Optional timeout in minutes (default: 60)

Requires API key authentication.

### Example Usage

```python
import os
from skylight_sdk import Skylight


with Skylight(
    apikey=os.getenv("SKYLIGHT_APIKEY", ""),
) as skylight:

    res = skylight.windows.start()

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `request`                                                           | [models.InstanceRequest](../../models/instancerequest.md)           | :heavy_check_mark:                                                  | The request object to use for the request.                          |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.InstanceStartResponse](../../models/instancestartresponse.md)**

### Errors

| Error Type                    | Status Code                   | Content Type                  |
| ----------------------------- | ----------------------------- | ----------------------------- |
| models.ForbiddenErrorResponse | 403                           | application/json              |
| models.HTTPValidationError    | 422                           | application/json              |
| models.ServerErrorResponse    | 500                           | application/json              |
| models.APIError               | 4XX, 5XX                      | \*/\*                         |

## pause

Requires API key authentication.

### Example Usage

```python
import os
from skylight_sdk import Skylight


with Skylight(
    apikey=os.getenv("SKYLIGHT_APIKEY", ""),
) as skylight:

    res = skylight.windows.pause(instance_id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `instance_id`                                                       | *str*                                                               | :heavy_check_mark:                                                  | N/A                                                                 |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.InactiveOperationResponse](../../models/inactiveoperationresponse.md)**

### Errors

| Error Type                    | Status Code                   | Content Type                  |
| ----------------------------- | ----------------------------- | ----------------------------- |
| models.ForbiddenErrorResponse | 403                           | application/json              |
| models.HTTPValidationError    | 422                           | application/json              |
| models.ServerErrorResponse    | 500                           | application/json              |
| models.APIError               | 4XX, 5XX                      | \*/\*                         |

## resume

Requires API key authentication.

### Example Usage

```python
import os
from skylight_sdk import Skylight


with Skylight(
    apikey=os.getenv("SKYLIGHT_APIKEY", ""),
) as skylight:

    res = skylight.windows.resume(instance_id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `instance_id`                                                       | *str*                                                               | :heavy_check_mark:                                                  | N/A                                                                 |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.ActiveOperationResponse](../../models/activeoperationresponse.md)**

### Errors

| Error Type                    | Status Code                   | Content Type                  |
| ----------------------------- | ----------------------------- | ----------------------------- |
| models.ForbiddenErrorResponse | 403                           | application/json              |
| models.HTTPValidationError    | 422                           | application/json              |
| models.ServerErrorResponse    | 500                           | application/json              |
| models.APIError               | 4XX, 5XX                      | \*/\*                         |

## terminate

Requires API key authentication.

### Example Usage

```python
import os
from skylight_sdk import Skylight


with Skylight(
    apikey=os.getenv("SKYLIGHT_APIKEY", ""),
) as skylight:

    res = skylight.windows.terminate(instance_id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `instance_id`                                                       | *str*                                                               | :heavy_check_mark:                                                  | N/A                                                                 |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.InactiveOperationResponse](../../models/inactiveoperationresponse.md)**

### Errors

| Error Type                    | Status Code                   | Content Type                  |
| ----------------------------- | ----------------------------- | ----------------------------- |
| models.ForbiddenErrorResponse | 403                           | application/json              |
| models.HTTPValidationError    | 422                           | application/json              |
| models.ServerErrorResponse    | 500                           | application/json              |
| models.APIError               | 4XX, 5XX                      | \*/\*                         |

## state

Requires API key authentication.

### Example Usage

```python
import os
from skylight_sdk import Skylight


with Skylight(
    apikey=os.getenv("SKYLIGHT_APIKEY", ""),
) as skylight:

    res = skylight.windows.state(instance_id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `instance_id`                                                       | *str*                                                               | :heavy_check_mark:                                                  | N/A                                                                 |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.InstanceStatusResponse](../../models/instancestatusresponse.md)**

### Errors

| Error Type                    | Status Code                   | Content Type                  |
| ----------------------------- | ----------------------------- | ----------------------------- |
| models.ForbiddenErrorResponse | 403                           | application/json              |
| models.HTTPValidationError    | 422                           | application/json              |
| models.ServerErrorResponse    | 500                           | application/json              |
| models.APIError               | 4XX, 5XX                      | \*/\*                         |

## instances

Requires API key authentication.

### Example Usage

```python
import os
from skylight_sdk import Skylight


with Skylight(
    apikey=os.getenv("SKYLIGHT_APIKEY", ""),
) as skylight:

    res = skylight.windows.instances()

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.InstancesListResponse](../../models/instanceslistresponse.md)**

### Errors

| Error Type                    | Status Code                   | Content Type                  |
| ----------------------------- | ----------------------------- | ----------------------------- |
| models.ForbiddenErrorResponse | 403                           | application/json              |
| models.ServerErrorResponse    | 500                           | application/json              |
| models.APIError               | 4XX, 5XX                      | \*/\*                         |