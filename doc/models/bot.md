
# Bot

*This model accepts additional fields of type object.*

## Structure

`Bot`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `AppId` | `string` | Required | **Constraints**: *Pattern*: `^A[A-Z0-9]{1,}$` |
| `Deleted` | `bool` | Required | - |
| `Icons` | [`Icons`](../../doc/models/icons.md) | Required | - |
| `Id` | `string` | Required | **Constraints**: *Pattern*: `^B[A-Z0-9]{8,}$` |
| `Name` | `string` | Required | - |
| `Updated` | `int` | Required | - |
| `UserId` | `string` | Optional | **Constraints**: *Pattern*: `^[UW][A-Z0-9]{2,}$` |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example (as JSON)

```json
{
  "app_id": "app_id2",
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
  "id": "id4",
  "name": "name4",
  "updated": 186,
  "user_id": "user_id2",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

