# Agent
(*agent*)

## Overview

### Available Operations

* [run](#run) - Run Agent
* [stop](#stop) - Stop Agent Endpoint
* [status](#status) - Get Agent Status Endpoint

## run

Run a loop with Anthropic's computer use agent to perform tasks on the VM.

Requires API key authentication.

### Example Usage

```python
import os
from skylight_sdk import Skylight


with Skylight(
    server_url="https://api.example.com",
    apikey=os.getenv("SKYLIGHT_APIKEY", ""),
) as skylight:

    res = skylight.agent.run(instance_id="<id>", query="Search for something on the VM")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `instance_id`                                                       | *str*                                                               | :heavy_check_mark:                                                  | N/A                                                                 |
| `query`                                                             | *str*                                                               | :heavy_check_mark:                                                  | N/A                                                                 |
| `messages`                                                          | List[[models.Messages](../../models/messages.md)]                   | :heavy_minus_sign:                                                  | N/A                                                                 |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.StandardResponse](../../models/standardresponse.md)**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| models.HTTPValidationError | 422                        | application/json           |
| models.ErrorResponse       | 500                        | application/json           |
| models.APIError            | 4XX, 5XX                   | \*/\*                      |

## stop

Stop a running agent for a specific instance.

Requires API key authentication.

### Example Usage

```python
import os
from skylight_sdk import Skylight


with Skylight(
    server_url="https://api.example.com",
    apikey=os.getenv("SKYLIGHT_APIKEY", ""),
) as skylight:

    res = skylight.agent.stop(instance_id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `instance_id`                                                       | *str*                                                               | :heavy_check_mark:                                                  | N/A                                                                 |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.StandardResponse](../../models/standardresponse.md)**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| models.ErrorResponse       | 404                        | application/json           |
| models.HTTPValidationError | 422                        | application/json           |
| models.ErrorResponse       | 500                        | application/json           |
| models.APIError            | 4XX, 5XX                   | \*/\*                      |

## status

Get the current status of an agent for a specific instance.

Requires API key authentication.

### Example Usage

```python
import os
from skylight_sdk import Skylight


with Skylight(
    server_url="https://api.example.com",
    apikey=os.getenv("SKYLIGHT_APIKEY", ""),
) as skylight:

    res = skylight.agent.status(agent_id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `agent_id`                                                          | *str*                                                               | :heavy_check_mark:                                                  | N/A                                                                 |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.StandardResponse](../../models/standardresponse.md)**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| models.ErrorResponse       | 404                        | application/json           |
| models.HTTPValidationError | 422                        | application/json           |
| models.ErrorResponse       | 500                        | application/json           |
| models.APIError            | 4XX, 5XX                   | \*/\*                      |