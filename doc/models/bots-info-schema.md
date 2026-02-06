
# Bots Info Schema

Schema for successful response from bots.info method

*This model accepts additional fields of type object.*

## Structure

`BotsInfoSchema`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Bot` | [`Bot`](../../doc/models/bot.md) | Required | - |
| `Ok` | `string` | Required, Constant | **Value**: `"True"` |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example (as JSON)

```json
{
  "bot": {
    "app_id": "app_id0",
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
    "id": "id6",
    "name": "name6",
    "updated": 214,
    "user_id": "user_id4",
    "exampleAdditionalProperty": {
      "key1": "val1",
      "key2": "val2"
    }
  },
  "ok": "True",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

