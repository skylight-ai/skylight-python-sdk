# FileUploadResponse

Response when a file is successfully uploaded to a VM


## Fields

| Field                                   | Type                                    | Required                                | Description                             | Example                                 |
| --------------------------------------- | --------------------------------------- | --------------------------------------- | --------------------------------------- | --------------------------------------- |
| `status`                                | *str*                                   | :heavy_check_mark:                      | Status of the operation                 | success                                 |
| `message`                               | *str*                                   | :heavy_check_mark:                      | Human-readable status message           | File uploaded successfully              |
| `file_path`                             | *str*                                   | :heavy_check_mark:                      | Path where the file was saved on the VM | C:\Users\Public\Downloads\file.pdf      |