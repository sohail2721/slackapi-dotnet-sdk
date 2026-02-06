
# Api Permissions Scopes List Success Schema

Schema for successful response api.permissions.scopes.list method

*This model accepts additional fields of type object.*

## Structure

`ApiPermissionsScopesListSuccessSchema`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Ok` | `string` | Required, Constant | **Value**: `"True"` |
| `Scopes` | [`Scopes`](../../doc/models/scopes.md) | Required | - |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example (as JSON)

```json
{
  "ok": "True",
  "scopes": {
    "app_home": [
      "app_home0",
      "app_home1",
      "app_home2"
    ],
    "channel": [
      "channel2",
      "channel1"
    ],
    "group": [
      "group1"
    ],
    "im": [
      "im1",
      "im2",
      "im3"
    ],
    "mpim": [
      "mpim2"
    ],
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

