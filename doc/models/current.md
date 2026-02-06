
# Current

*This model accepts additional fields of type object.*

## Structure

`Current`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `DateStarted` | `int` | Required | - |
| `TeamId` | `string` | Required | - |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example (as JSON)

```json
{
  "date_started": 30,
  "team_id": "team_id4",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

