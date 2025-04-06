# DragRequest


## Fields

| Field                                                                                | Type                                                                                 | Required                                                                             | Description                                                                          |
| ------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------ |
| `path`                                                                               | List[Dict[str, *int*]]                                                               | :heavy_check_mark:                                                                   | N/A                                                                                  |
| `button`                                                                             | [Optional[models.DragRequestButton]](../models/dragrequestbutton.md)                 | :heavy_minus_sign:                                                                   | N/A                                                                                  |
| `step`                                                                               | *OptionalNullable[int]*                                                              | :heavy_minus_sign:                                                                   | Optional step size for drag movements. If not provided, movement will be continuous. |