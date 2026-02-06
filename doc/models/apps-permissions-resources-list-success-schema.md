
# Apps Permissions Resources List Success Schema

Schema for successful response apps.permissions.resources.list method

*This model accepts additional fields of type object.*

## Structure

`AppsPermissionsResourcesListSuccessSchema`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Ok` | `string` | Required, Constant | **Value**: `"True"` |
| `Resources` | [`List<Resource>`](../../doc/models/resource.md) | Required | - |
| `ResponseMetadata` | [`ResponseMetadata`](../../doc/models/response-metadata.md) | Optional | - |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example (as JSON)

```json
{
  "ok": "True",
  "resources": [
    {
      "id": "id0",
      "type": "type0",
      "exampleAdditionalProperty": {
        "key1": "val1",
        "key2": "val2"
      }
    }
  ],
  "response_metadata": {
    "next_cursor": "next_cursor2",
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

