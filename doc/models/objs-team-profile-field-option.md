
# Objs Team Profile Field Option

*This model accepts additional fields of type object.*

## Structure

`ObjsTeamProfileFieldOption`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `IsCustom` | `bool?` | Optional | - |
| `IsMultipleEntry` | `bool?` | Optional | - |
| `IsProtected` | `bool?` | Optional | - |
| `IsScim` | `bool?` | Optional | - |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example (as JSON)

```json
{
  "is_custom": false,
  "is_multiple_entry": false,
  "is_protected": false,
  "is_scim": false,
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

