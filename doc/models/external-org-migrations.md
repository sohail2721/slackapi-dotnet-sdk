
# External Org Migrations

*This model accepts additional fields of type object.*

## Structure

`ExternalOrgMigrations`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Current` | [`List<Current>`](../../doc/models/current.md) | Required | - |
| `DateUpdated` | `int` | Required | - |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example (as JSON)

```json
{
  "current": [
    {
      "date_started": 84,
      "team_id": "team_id0",
      "exampleAdditionalProperty": {
        "key1": "val1",
        "key2": "val2"
      }
    }
  ],
  "date_updated": 8,
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

