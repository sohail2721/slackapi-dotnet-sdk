
# Scopes

*This model accepts additional fields of type object.*

## Structure

`Scopes`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `AppHome` | `List<string>` | Optional | - |
| `Channel` | `List<string>` | Optional | - |
| `Group` | `List<string>` | Optional | - |
| `Im` | `List<string>` | Optional | - |
| `Mpim` | `List<string>` | Optional | - |
| `Team` | `List<string>` | Optional | - |
| `User` | `List<string>` | Optional | - |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example (as JSON)

```json
{
  "app_home": [
    "app_home2",
    "app_home1",
    "app_home0"
  ],
  "channel": [
    "channel0",
    "channel9"
  ],
  "group": [
    "group9"
  ],
  "im": [
    "im1",
    "im0",
    "im9"
  ],
  "mpim": [
    "mpim0"
  ],
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

