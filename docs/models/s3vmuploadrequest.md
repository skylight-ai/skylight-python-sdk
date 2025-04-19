# S3VMUploadRequest


## Fields

| Field                                                                       | Type                                                                        | Required                                                                    | Description                                                                 |
| --------------------------------------------------------------------------- | --------------------------------------------------------------------------- | --------------------------------------------------------------------------- | --------------------------------------------------------------------------- |
| `s3_url`                                                                    | *str*                                                                       | :heavy_check_mark:                                                          | The S3 URL of the file to upload                                            |
| `file_name`                                                                 | *str*                                                                       | :heavy_check_mark:                                                          | Original name of the file                                                   |
| `file_type`                                                                 | *Optional[str]*                                                             | :heavy_minus_sign:                                                          | MIME type of the file                                                       |
| `target_path`                                                               | *Optional[str]*                                                             | :heavy_minus_sign:                                                          | Target path on the VM (defaults to Users/Administrator/Desktop/{file_name}) |