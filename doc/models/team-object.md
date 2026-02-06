
# Team Object

*This model accepts additional fields of type object.*

## Structure

`TeamObject`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Archived` | `bool?` | Optional | - |
| `AvatarBaseUrl` | `string` | Optional | - |
| `Created` | `int?` | Optional | - |
| `DateCreate` | `int?` | Optional | - |
| `Deleted` | `bool?` | Optional | - |
| `Description` | `string` | Optional | - |
| `Discoverable` | `object` | Optional | - |
| `Domain` | `string` | Required | - |
| `EmailDomain` | `string` | Required | - |
| `EnterpriseId` | `string` | Optional | **Constraints**: *Pattern*: `^[E][A-Z0-9]{8,}$` |
| `EnterpriseName` | `string` | Optional | - |
| `ExternalOrgMigrations` | [`ExternalOrgMigrations`](../../doc/models/external-org-migrations.md) | Optional | - |
| `HasComplianceExport` | `bool?` | Optional | - |
| `Icon` | [`ObjsIcon`](../../doc/models/objs-icon.md) | Required | - |
| `Id` | `string` | Required | **Constraints**: *Pattern*: `^[TE][A-Z0-9]{8,}$` |
| `IsAssigned` | `bool?` | Optional | - |
| `IsEnterprise` | `int?` | Optional | - |
| `IsOverStorageLimit` | `bool?` | Optional | - |
| `LimitTs` | `int?` | Optional | - |
| `Locale` | `string` | Optional | - |
| `MessagesCount` | `int?` | Optional | - |
| `MsgEditWindowMins` | `int?` | Optional | - |
| `Name` | `string` | Required | - |
| `OverIntegrationsLimit` | `bool?` | Optional | - |
| `OverStorageLimit` | `bool?` | Optional | - |
| `PayProdCur` | `string` | Optional | - |
| `Plan` | [`Plan?`](../../doc/models/plan.md) | Optional | - |
| `PrimaryOwner` | [`ObjsPrimaryOwner`](../../doc/models/objs-primary-owner.md) | Optional | - |
| `SsoProvider` | [`SsoProvider`](../../doc/models/sso-provider.md) | Optional | - |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example (as JSON)

```json
{
  "archived": false,
  "avatar_base_url": "avatar_base_url4",
  "created": 18,
  "date_create": 124,
  "deleted": false,
  "domain": "domain0",
  "email_domain": "email_domain4",
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
  "id": "id4",
  "name": "name4",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

