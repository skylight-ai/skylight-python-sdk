# Windows
(*windows*)

## Overview

### Available Operations

* [start](#start) - Start Vm
* [install](#install) - Install Chocolatey Packages
* [pause](#pause) - Pause Vm
* [resume](#resume) - Resume Vm
* [state](#state) - Get Vm Status
* [instances](#instances) - Get Instances
* [terminate](#terminate) - Terminate Vm

## start

Start a new Windows VM instance.

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
| `request`                                                           | [models.VMRequest](../../models/vmrequest.md)                       | :heavy_check_mark:                                                  | The request object to use for the request.                          |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.VMStartResponse](../../models/vmstartresponse.md)**

### Errors

| Error Type                    | Status Code                   | Content Type                  |
| ----------------------------- | ----------------------------- | ----------------------------- |
| models.ForbiddenErrorResponse | 403                           | application/json              |
| models.HTTPValidationError    | 422                           | application/json              |
| models.ServerErrorResponse    | 500                           | application/json              |
| models.APIError               | 4XX, 5XX                      | \*/\*                         |

## install

Install Chocolatey packages on a Windows VM. Find a list of packages here: https://community.chocolatey.org/packages.

Requires API key authentication.

### Example Usage

```python
import os
from skylight_sdk import Skylight


with Skylight(
    apikey=os.getenv("SKYLIGHT_APIKEY", ""),
) as skylight:

    res = skylight.windows.install(instance_id="<id>", packages=[
        "<value>",
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

**[models.VMPauseResponse](../../models/vmpauseresponse.md)**

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

**[models.VMResumeResponse](../../models/vmresumeresponse.md)**

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

**[models.VMStatusResponse](../../models/vmstatusresponse.md)**

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

**[models.VMInstancesListResponse](../../models/vminstanceslistresponse.md)**

### Errors

| Error Type                    | Status Code                   | Content Type                  |
| ----------------------------- | ----------------------------- | ----------------------------- |
| models.ForbiddenErrorResponse | 403                           | application/json              |
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

**[models.VMTerminateResponse](../../models/vmterminateresponse.md)**

### Errors

| Error Type                    | Status Code                   | Content Type                  |
| ----------------------------- | ----------------------------- | ----------------------------- |
| models.ForbiddenErrorResponse | 403                           | application/json              |
| models.HTTPValidationError    | 422                           | application/json              |
| models.ServerErrorResponse    | 500                           | application/json              |
| models.APIError               | 4XX, 5XX                      | \*/\*                         |