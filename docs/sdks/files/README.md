# Files
(*files*)

## Overview

### Available Operations

* [upload](#upload) - Upload To Vm
* [download](#download) - Get File

## upload

Upload a file from S3 to the VM

Takes an S3 URL (often from FileUploader component) and transfers it to the VM.
Updates the files.uploads array in the vm_instances table to track the file.

Requires API key authentication.

### Example Usage

```python
import os
from skylight_sdk import Skylight


with Skylight(
    apikey=os.getenv("SKYLIGHT_APIKEY", ""),
) as skylight:

    res = skylight.files.upload(instance_id="<id>", s3_url="https://needy-mallard.info/", file_name="example.file")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                   | Type                                                                        | Required                                                                    | Description                                                                 |
| --------------------------------------------------------------------------- | --------------------------------------------------------------------------- | --------------------------------------------------------------------------- | --------------------------------------------------------------------------- |
| `instance_id`                                                               | *str*                                                                       | :heavy_check_mark:                                                          | N/A                                                                         |
| `s3_url`                                                                    | *str*                                                                       | :heavy_check_mark:                                                          | The S3 URL of the file to upload                                            |
| `file_name`                                                                 | *str*                                                                       | :heavy_check_mark:                                                          | Original name of the file                                                   |
| `file_type`                                                                 | *Optional[str]*                                                             | :heavy_minus_sign:                                                          | MIME type of the file                                                       |
| `target_path`                                                               | *Optional[str]*                                                             | :heavy_minus_sign:                                                          | Target path on the VM (defaults to Users/Administrator/Desktop/{file_name}) |
| `retries`                                                                   | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)            | :heavy_minus_sign:                                                          | Configuration to override the default retry behavior of the client.         |

### Response

**[models.FileUploadResponse](../../models/fileuploadresponse.md)**

### Errors

| Error Type                         | Status Code                        | Content Type                       |
| ---------------------------------- | ---------------------------------- | ---------------------------------- |
| models.InteractModelsErrorResponse | 400                                | application/json                   |
| models.ForbiddenErrorResponse      | 403                                | application/json                   |
| models.HTTPValidationError         | 422                                | application/json                   |
| models.InteractModelsErrorResponse | 500                                | application/json                   |
| models.APIError                    | 4XX, 5XX                           | \*/\*                              |

## download

Get a secure download link for a file on the instance

Generates a presigned S3 URL for the client to download the file directly

Requires API key authentication.

### Example Usage

```python
import os
from skylight_sdk import Skylight


with Skylight(
    apikey=os.getenv("SKYLIGHT_APIKEY", ""),
) as skylight:

    res = skylight.files.download(instance_id="<id>", request_body={
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

**[models.FileDownloadResponse](../../models/filedownloadresponse.md)**

### Errors

| Error Type                         | Status Code                        | Content Type                       |
| ---------------------------------- | ---------------------------------- | ---------------------------------- |
| models.ForbiddenErrorResponse      | 403                                | application/json                   |
| models.HTTPValidationError         | 422                                | application/json                   |
| models.InteractModelsErrorResponse | 500                                | application/json                   |
| models.APIError                    | 4XX, 5XX                           | \*/\*                              |