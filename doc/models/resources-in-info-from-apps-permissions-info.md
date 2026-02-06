
# Resources in Info From Apps Permissions Info

*This model accepts additional fields of type object.*

## Structure

`ResourcesInInfoFromAppsPermissionsInfo`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `ExcludedIds` | `object` | Optional | - |
| `Ids` | `object` | Required | - |
| `Wildcard` | `bool?` | Optional | - |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example (as JSON)

```json
{
  "excluded_ids": [
    {
      "key1": "val1",
      "key2": "val2"
    }
  ],
  "ids": [
    {
      "key1": "val1",
      "key2": "val2"
    }
  ],
  "wildcard": false,
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

