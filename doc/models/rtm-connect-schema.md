
# Rtm Connect Schema

Schema for successful response from rtm.connect method

*This model accepts additional fields of type object.*

## Structure

`RtmConnectSchema`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Ok` | `string` | Required, Constant | **Value**: `"True"` |
| `Self` | [`Self`](../../doc/models/self.md) | Required | - |
| `Team` | [`Team1`](../../doc/models/team-1.md) | Required | - |
| `Url` | `string` | Required | - |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example (as JSON)

```json
{
  "ok": "True",
  "self": {
    "id": "id8",
    "name": "name8",
    "exampleAdditionalProperty": {
      "key1": "val1",
      "key2": "val2"
    }
  },
  "team": {
    "domain": "domain6",
    "id": "id0",
    "name": "name0",
    "exampleAdditionalProperty": {
      "key1": "val1",
      "key2": "val2"
    }
  },
  "url": "url8",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

