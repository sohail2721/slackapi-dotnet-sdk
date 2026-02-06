# Calls Participants

```csharp
CallsParticipantsController callsParticipantsController = client.CallsParticipantsController;
```

## Class Name

`CallsParticipantsController`

## Methods

* [Calls Participants Add](../../doc/controllers/calls-participants.md#calls-participants-add)
* [Calls Participants Remove](../../doc/controllers/calls-participants.md#calls-participants-remove)


# Calls Participants Add

Registers new participants added to a Call.

API method documentation: [https://api.slack.com/methods/calls.participants.add](https://api.slack.com/methods/calls.participants.add)

```csharp
CallsParticipantsAddAsync(
    string token,
    string id,
    string users)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `calls:write` |
| `id` | `string` | Form, Required | `id` returned by the [`calls.add`](/methods/calls.add) method. |
| `users` | `string` | Form, Required | The list of users to add as participants in the Call. [Read more on how to specify users here](/apis/calls#users). |

## Requires scope

### slackAuth

`calls:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.DefaultSuccessTemplate](../../doc/models/default-success-template.md).

## Example Usage

```csharp
string token = "token6";
string id = "id0";
string users = "users6";
try
{
    ApiResponse<DefaultSuccessTemplate> result = await callsParticipantsController.CallsParticipantsAddAsync(
        token,
        id,
        users
    );
}
catch (ApiException e)
{
    Console.WriteLine(e.Message);
    if (e is DefaultErrorTemplateException)
    {
       // TODO: Handle DefaultErrorTemplateException exception here
    }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`DefaultErrorTemplateException`](../../doc/models/default-error-template-exception.md) |


# Calls Participants Remove

Registers participants removed from a Call.

API method documentation: [https://api.slack.com/methods/calls.participants.remove](https://api.slack.com/methods/calls.participants.remove)

```csharp
CallsParticipantsRemoveAsync(
    string token,
    string id,
    string users)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `calls:write` |
| `id` | `string` | Form, Required | `id` returned by the [`calls.add`](/methods/calls.add) method. |
| `users` | `string` | Form, Required | The list of users to remove as participants in the Call. [Read more on how to specify users here](/apis/calls#users). |

## Requires scope

### slackAuth

`calls:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.DefaultSuccessTemplate](../../doc/models/default-success-template.md).

## Example Usage

```csharp
string token = "token6";
string id = "id0";
string users = "users6";
try
{
    ApiResponse<DefaultSuccessTemplate> result = await callsParticipantsController.CallsParticipantsRemoveAsync(
        token,
        id,
        users
    );
}
catch (ApiException e)
{
    Console.WriteLine(e.Message);
    if (e is DefaultErrorTemplateException)
    {
       // TODO: Handle DefaultErrorTemplateException exception here
    }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`DefaultErrorTemplateException`](../../doc/models/default-error-template-exception.md) |

