
# Scheduled Message

*This model accepts additional fields of type object.*

## Structure

`ScheduledMessage`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `ChannelId` | `string` | Required | **Constraints**: *Pattern*: `^[C][A-Z0-9]{2,}$` |
| `DateCreated` | `int` | Required | - |
| `Id` | `string` | Required | **Constraints**: *Pattern*: `^[Q][A-Z0-9]{8,}$` |
| `PostAt` | `int` | Required | - |
| `Text` | `string` | Optional | - |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example (as JSON)

```json
{
  "channel_id": "channel_id4",
  "date_created": 228,
  "id": "id8",
  "post_at": 128,
  "text": "text8",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

