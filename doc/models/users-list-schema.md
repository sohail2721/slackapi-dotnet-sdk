
# Users List Schema

Schema for successful response from users.list method

*This model accepts additional fields of type object.*

## Structure

`UsersListSchema`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `CacheTs` | `int` | Required | - |
| `Members` | `object` | Required | **Constraints**: *Minimum Items*: `1`, *Unique Items Required* |
| `Ok` | `string` | Required, Constant | **Value**: `"True"` |
| `ResponseMetadata` | `object` | Optional | - |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example (as JSON)

```json
{
  "cache_ts": 154,
  "members": [
    {
      "key1": "val1",
      "key2": "val2"
    },
    {
      "key1": "val1",
      "key2": "val2"
    }
  ],
  "ok": "True",
  "response_metadata": {
    "key1": "val1",
    "key2": "val2"
  },
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

