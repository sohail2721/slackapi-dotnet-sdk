
# Mpim

*This model accepts additional fields of type object.*

## Structure

`Mpim`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Resources` | [`ResourcesInInfoFromAppsPermissionsInfo`](../../doc/models/resources-in-info-from-apps-permissions-info.md) | Optional | - |
| `Scopes` | `List<string>` | Optional | - |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example (as JSON)

```json
{
  "resources": {
    "excluded_ids": [
      {
        "key1": "val1",
        "key2": "val2"
      },
      {
        "key1": "val1",
        "key2": "val2"
      },
      {
        "key1": "val1",
        "key2": "val2"
      }
    ],
    "ids": [
      {
        "key1": "val1",
        "key2": "val2"
      },
      {
        "key1": "val1",
        "key2": "val2"
      },
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
  },
  "scopes": [
    "scopes4",
    "scopes3",
    "scopes2"
  ],
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

