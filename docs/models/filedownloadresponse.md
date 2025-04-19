# FileDownloadResponse

Response containing a presigned URL to download a file


## Fields

| Field                                          | Type                                           | Required                                       | Description                                    | Example                                        |
| ---------------------------------------------- | ---------------------------------------------- | ---------------------------------------------- | ---------------------------------------------- | ---------------------------------------------- |
| `status`                                       | *str*                                          | :heavy_check_mark:                             | Status of the operation                        | success                                        |
| `message`                                      | *str*                                          | :heavy_check_mark:                             | Human-readable status message                  | File download URL generated successfully       |
| `download_url`                                 | *str*                                          | :heavy_check_mark:                             | Presigned URL to download the file             | https://s3.amazonaws.com/bucket/file?token=... |