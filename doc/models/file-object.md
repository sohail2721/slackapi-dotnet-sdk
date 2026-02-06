
# File Object

*This model accepts additional fields of type object.*

## Structure

`FileObject`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Channels` | `List<string>` | Optional | **Constraints**: *Unique Items Required*, *Pattern*: `^[C][A-Z0-9]{2,}$` |
| `CommentsCount` | `int?` | Optional | - |
| `Created` | `int?` | Optional | - |
| `DateDelete` | `int?` | Optional | - |
| `DisplayAsBot` | `bool?` | Optional | - |
| `Editable` | `bool?` | Optional | - |
| `Editor` | `string` | Optional | **Constraints**: *Pattern*: `^[UW][A-Z0-9]{2,}$` |
| `ExternalId` | `string` | Optional | - |
| `ExternalType` | `string` | Optional | - |
| `ExternalUrl` | `string` | Optional | - |
| `Filetype` | `string` | Optional | - |
| `Groups` | `List<string>` | Optional | **Constraints**: *Unique Items Required*, *Pattern*: `^[G][A-Z0-9]{8,}$` |
| `HasRichPreview` | `bool?` | Optional | - |
| `Id` | `string` | Optional | **Constraints**: *Pattern*: `^[F][A-Z0-9]{8,}$` |
| `ImageExifRotation` | `int?` | Optional | - |
| `Ims` | `List<string>` | Optional | **Constraints**: *Unique Items Required*, *Pattern*: `^[D][A-Z0-9]{8,}$` |
| `IsExternal` | `bool?` | Optional | - |
| `IsPublic` | `bool?` | Optional | - |
| `IsStarred` | `bool?` | Optional | - |
| `IsTombstoned` | `bool?` | Optional | - |
| `LastEditor` | `string` | Optional | **Constraints**: *Pattern*: `^[UW][A-Z0-9]{2,}$` |
| `Mimetype` | `string` | Optional | - |
| `Mode` | `string` | Optional | - |
| `Name` | `string` | Optional | - |
| `NonOwnerEditable` | `bool?` | Optional | - |
| `NumStars` | `int?` | Optional | - |
| `OriginalH` | `int?` | Optional | - |
| `OriginalW` | `int?` | Optional | - |
| `Permalink` | `string` | Optional | - |
| `PermalinkPublic` | `string` | Optional | - |
| `PinnedInfo` | `object` | Optional | - |
| `PinnedTo` | `List<string>` | Optional | **Constraints**: *Pattern*: `^[CGD][A-Z0-9]{8,}$` |
| `PrettyType` | `string` | Optional | - |
| `Preview` | `string` | Optional | - |
| `PublicUrlShared` | `bool?` | Optional | - |
| `Reactions` | [`List<ReactionObject>`](../../doc/models/reaction-object.md) | Optional | - |
| `Shares` | [`Shares`](../../doc/models/shares.md) | Optional | - |
| `Size` | `int?` | Optional | - |
| `SourceTeam` | `string` | Optional | **Constraints**: *Pattern*: `^[T][A-Z0-9]{2,}$` |
| `State` | `string` | Optional | - |
| `Thumb1024` | `string` | Optional | - |
| `Thumb1024H` | `int?` | Optional | - |
| `Thumb1024W` | `int?` | Optional | - |
| `Thumb160` | `string` | Optional | - |
| `Thumb360` | `string` | Optional | - |
| `Thumb360H` | `int?` | Optional | - |
| `Thumb360W` | `int?` | Optional | - |
| `Thumb480` | `string` | Optional | - |
| `Thumb480H` | `int?` | Optional | - |
| `Thumb480W` | `int?` | Optional | - |
| `Thumb64` | `string` | Optional | - |
| `Thumb720` | `string` | Optional | - |
| `Thumb720H` | `int?` | Optional | - |
| `Thumb720W` | `int?` | Optional | - |
| `Thumb80` | `string` | Optional | - |
| `Thumb800` | `string` | Optional | - |
| `Thumb800H` | `int?` | Optional | - |
| `Thumb800W` | `int?` | Optional | - |
| `Thumb960` | `string` | Optional | - |
| `Thumb960H` | `int?` | Optional | - |
| `Thumb960W` | `int?` | Optional | - |
| `ThumbTiny` | `string` | Optional | - |
| `Timestamp` | `int?` | Optional | - |
| `Title` | `string` | Optional | - |
| `Updated` | `int?` | Optional | - |
| `UrlPrivate` | `string` | Optional | - |
| `UrlPrivateDownload` | `string` | Optional | - |
| `User` | `string` | Optional | - |
| `UserTeam` | `string` | Optional | **Constraints**: *Pattern*: `^[T][A-Z0-9]{2,}$` |
| `Username` | `string` | Optional | - |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example (as JSON)

```json
{
  "channels": [
    "channels3",
    "channels2",
    "channels1"
  ],
  "comments_count": 94,
  "created": 2,
  "date_delete": 156,
  "display_as_bot": false,
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

