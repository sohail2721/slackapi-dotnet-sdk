
# Bot Profile Object

*This model accepts additional fields of type object.*

## Structure

`BotProfileObject`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `AppId` | `string` | Required | **Constraints**: *Pattern*: `^A[A-Z0-9]{1,}$` |
| `Deleted` | `bool` | Required | - |
| `Icons` | [`Icons`](../../doc/models/icons.md) | Required | - |
| `Id` | `string` | Required | **Constraints**: *Pattern*: `^B[A-Z0-9]{8,}$` |
| `Name` | `string` | Required | - |
| `TeamId` | `string` | Required | **Constraints**: *Pattern*: `^[T][A-Z0-9]{2,}$` |
| `Updated` | `int` | Required | - |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example (as JSON)

```json
{
  "app_id": "app_id4",
  "deleted": false,
  "icons": {
    "image_36": "image_362",
    "image_48": "image_488",
    "image_72": "image_722",
    "exampleAdditionalProperty": {
      "key1": "val1",
      "key2": "val2"
    }
  },
  "id": "id2",
  "name": "name2",
  "team_id": "team_id6",
  "updated": 94,
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

