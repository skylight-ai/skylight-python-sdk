# AgentStatusResponse


## Fields

| Field                                    | Type                                     | Required                                 | Description                              | Example                                  |
| ---------------------------------------- | ---------------------------------------- | ---------------------------------------- | ---------------------------------------- | ---------------------------------------- |
| `agent_status`                           | *str*                                    | :heavy_check_mark:                       | Current status of the agent              | running                                  |
| `is_running`                             | *bool*                                   | :heavy_check_mark:                       | Whether the agent is currently running   | true                                     |
| `total_steps`                            | *int*                                    | :heavy_check_mark:                       | Total number of steps executed           | 5                                        |
| `step_count`                             | *int*                                    | :heavy_check_mark:                       | Number of steps in memory                | 5                                        |
| `final_summary`                          | *OptionalNullable[str]*                  | :heavy_minus_sign:                       | Final summary of agent execution         |                                          |
| `files`                                  | List[[models.Files](../models/files.md)] | :heavy_check_mark:                       | List of files downloaded by the agent    |                                          |
| `steps`                                  | List[*str*]                              | :heavy_check_mark:                       | List of steps executed by the agent      |                                          |
| `created_at`                             | *str*                                    | :heavy_check_mark:                       | Timestamp when the agent was created     |                                          |
| `query`                                  | *str*                                    | :heavy_check_mark:                       | Original query given to the agent        |                                          |
| `agent_id`                               | *str*                                    | :heavy_check_mark:                       | Unique identifier for the agent          |                                          |