
# Team Info Schema

Schema for successful response from team.info method

*This model accepts additional fields of type object.*

## Structure

`TeamInfoSchema`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Ok` | `string` | Required, Constant | **Value**: `"True"` |
| `Team` | [`TeamObject`](../../doc/models/team-object.md) | Required | - |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example (as JSON)

```json
{
  "ok": "True",
  "team": {
    "archived": false,
    "avatar_base_url": "avatar_base_url0",
    "created": 212,
    "date_create": 62,
    "deleted": false,
    "domain": "domain6",
    "email_domain": "email_domain0",
    "icon": {
      "image_102": "image_1020",
      "image_132": "image_1326",
      "image_230": "image_2308",
      "image_34": "image_340",
      "image_44": "image_440",
      "exampleAdditionalProperty": {
        "key1": "val1",
        "key2": "val2"
      }
    },
    "id": "id0",
    "name": "name0",
    "exampleAdditionalProperty": {
      "key1": "val1",
      "key2": "val2"
    }
  },
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

