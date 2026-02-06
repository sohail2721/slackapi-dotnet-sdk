
# Getting Started with Slack Web API

## Introduction

One way to interact with the Slack platform is its HTTP RPC-based Web API, a collection of methods requiring OAuth 2.0-based user, bot, or workspace tokens blessed with related OAuth scopes.

Learn more about the Slack Web API: [https://api.slack.com/web](https://api.slack.com/web)

## Install the Package

If you are building with .NET CLI tools then you can also use the following command:

```bash
dotnet add package SlackapiSDK --version 1.0.0
```

You can also view the package at:
https://www.nuget.org/packages/SlackapiSDK/1.0.0

## Initialize the API Client

**_Note:_** Documentation for the client can be found [here.](https://www.github.com/sohail2721/slackapi-dotnet-sdk/tree/1.0.0/doc/client.md)

The following parameters are configurable for the API Client:

| Parameter | Type | Description |
|  --- | --- | --- |
| Environment | [`Environment`](https://www.github.com/sohail2721/slackapi-dotnet-sdk/tree/1.0.0/README.md#environments) | The API environment. <br> **Default: `Environment.Production`** |
| Timeout | `TimeSpan` | Http client timeout.<br>*Default*: `TimeSpan.FromSeconds(30)` |
| HttpClientConfiguration | [`Action<HttpClientConfiguration.Builder>`](https://www.github.com/sohail2721/slackapi-dotnet-sdk/tree/1.0.0/doc/http-client-configuration-builder.md) | Action delegate that configures the HTTP client by using the HttpClientConfiguration.Builder for customizing API call settings.<br>*Default*: `new HttpClient()` |
| LogBuilder | [`LogBuilder`](https://www.github.com/sohail2721/slackapi-dotnet-sdk/tree/1.0.0/doc/log-builder.md) | Represents the logging configuration builder for API calls |
| AuthorizationCodeAuth | [`AuthorizationCodeAuth`](https://www.github.com/sohail2721/slackapi-dotnet-sdk/tree/1.0.0/doc/auth/oauth-2-authorization-code-grant.md) | The Credentials Setter for OAuth 2 Authorization Code Grant |

The API client can be initialized as follows:

### Code-Based Initialization

```csharp
using Microsoft.Extensions.Logging;
using SlackWebApi.Standard;
using SlackWebApi.Standard.Authentication;
using SlackWebApi.Standard.Models;
using System.Collections.Generic;

namespace ConsoleApp;

SlackWebApiClient client = new SlackWebApiClient.Builder()
    .AuthorizationCodeAuth(
        new AuthorizationCodeAuthModel.Builder(
            "OAuthClientId",
            "OAuthClientSecret",
            "OAuthRedirectUri"
        )
        .OauthScopes(
            new List<OauthScope>
            {
                OauthScope.Admin,
                OauthScope.AdminAppsread,
            })
        .Build())
    .HttpClientConfig(httpClientConfig =>
        httpClientConfig.Timeout(TimeSpan.FromSeconds(100)))
    .Environment(SlackWebApi.Standard.Environment.Production)
    .LoggingConfig(config => config
        .LogLevel(LogLevel.Information)
        .RequestConfig(reqConfig => reqConfig.Body(true))
        .ResponseConfig(respConfig => respConfig.Headers(true))
    )
    .Build();
```

### Configuration-Based Initialization

```csharp
using SlackWebApi.Standard;
using Microsoft.Extensions.Configuration;

namespace ConsoleApp;

// Build the IConfiguration using .NET conventions (JSON, environment, etc.)
var configuration = new ConfigurationBuilder()
    .AddJsonFile("config.json")
    .AddEnvironmentVariables() // [optional] read environment variables
    .Build();

// Instantiate your SDK and configure it from IConfiguration
var client = SlackWebApiClient
    .FromConfiguration(configuration.GetSection("SlackWebApi"));
```

See the [Configuration-Based Initialization](https://www.github.com/sohail2721/slackapi-dotnet-sdk/tree/1.0.0/doc/configuration-based-initialization.md) section for details.

## Environments

The SDK can be configured to use a different environment for making API calls. Available environments are:

### Fields

| Name | Description |
|  --- | --- |
| Production | **Default** |

## Authorization

This API uses the following authentication schemes.

* [`slackAuth (OAuth 2 Authorization Code Grant)`](https://www.github.com/sohail2721/slackapi-dotnet-sdk/tree/1.0.0/doc/auth/oauth-2-authorization-code-grant.md)

## List of APIs

* [Admin Apps](https://www.github.com/sohail2721/slackapi-dotnet-sdk/tree/1.0.0/doc/controllers/admin-apps.md)
* [Admin Apps Approved](https://www.github.com/sohail2721/slackapi-dotnet-sdk/tree/1.0.0/doc/controllers/admin-apps-approved.md)
* [Admin Apps Requests](https://www.github.com/sohail2721/slackapi-dotnet-sdk/tree/1.0.0/doc/controllers/admin-apps-requests.md)
* [Admin Apps Restricted](https://www.github.com/sohail2721/slackapi-dotnet-sdk/tree/1.0.0/doc/controllers/admin-apps-restricted.md)
* [Admin Conversations](https://www.github.com/sohail2721/slackapi-dotnet-sdk/tree/1.0.0/doc/controllers/admin-conversations.md)
* [Admin Conversations Ekm](https://www.github.com/sohail2721/slackapi-dotnet-sdk/tree/1.0.0/doc/controllers/admin-conversations-ekm.md)
* [Admin Conversations Restrict Access](https://www.github.com/sohail2721/slackapi-dotnet-sdk/tree/1.0.0/doc/controllers/admin-conversations-restrict-access.md)
* [Admin Emoji](https://www.github.com/sohail2721/slackapi-dotnet-sdk/tree/1.0.0/doc/controllers/admin-emoji.md)
* [Admin Invite Requests](https://www.github.com/sohail2721/slackapi-dotnet-sdk/tree/1.0.0/doc/controllers/admin-invite-requests.md)
* [Admin Invite Requests Approved](https://www.github.com/sohail2721/slackapi-dotnet-sdk/tree/1.0.0/doc/controllers/admin-invite-requests-approved.md)
* [Admin Invite Requests Denied](https://www.github.com/sohail2721/slackapi-dotnet-sdk/tree/1.0.0/doc/controllers/admin-invite-requests-denied.md)
* [Admin Teams Admins](https://www.github.com/sohail2721/slackapi-dotnet-sdk/tree/1.0.0/doc/controllers/admin-teams-admins.md)
* [Admin Teams](https://www.github.com/sohail2721/slackapi-dotnet-sdk/tree/1.0.0/doc/controllers/admin-teams.md)
* [Admin Teams Owners](https://www.github.com/sohail2721/slackapi-dotnet-sdk/tree/1.0.0/doc/controllers/admin-teams-owners.md)
* [Admin Teams Settings](https://www.github.com/sohail2721/slackapi-dotnet-sdk/tree/1.0.0/doc/controllers/admin-teams-settings.md)
* [Admin Usergroups](https://www.github.com/sohail2721/slackapi-dotnet-sdk/tree/1.0.0/doc/controllers/admin-usergroups.md)
* [Admin Users](https://www.github.com/sohail2721/slackapi-dotnet-sdk/tree/1.0.0/doc/controllers/admin-users.md)
* [Admin Users Session](https://www.github.com/sohail2721/slackapi-dotnet-sdk/tree/1.0.0/doc/controllers/admin-users-session.md)
* [Api](https://www.github.com/sohail2721/slackapi-dotnet-sdk/tree/1.0.0/doc/controllers/api.md)
* [Apps Event Authorizations](https://www.github.com/sohail2721/slackapi-dotnet-sdk/tree/1.0.0/doc/controllers/apps-event-authorizations.md)
* [Apps Permissions](https://www.github.com/sohail2721/slackapi-dotnet-sdk/tree/1.0.0/doc/controllers/apps-permissions.md)
* [Apps Permissions Resources](https://www.github.com/sohail2721/slackapi-dotnet-sdk/tree/1.0.0/doc/controllers/apps-permissions-resources.md)
* [Apps Permissions Scopes](https://www.github.com/sohail2721/slackapi-dotnet-sdk/tree/1.0.0/doc/controllers/apps-permissions-scopes.md)
* [Apps Permissions Users](https://www.github.com/sohail2721/slackapi-dotnet-sdk/tree/1.0.0/doc/controllers/apps-permissions-users.md)
* [Apps](https://www.github.com/sohail2721/slackapi-dotnet-sdk/tree/1.0.0/doc/controllers/apps.md)
* [Auth](https://www.github.com/sohail2721/slackapi-dotnet-sdk/tree/1.0.0/doc/controllers/auth.md)
* [Bots](https://www.github.com/sohail2721/slackapi-dotnet-sdk/tree/1.0.0/doc/controllers/bots.md)
* [Calls](https://www.github.com/sohail2721/slackapi-dotnet-sdk/tree/1.0.0/doc/controllers/calls.md)
* [Calls Participants](https://www.github.com/sohail2721/slackapi-dotnet-sdk/tree/1.0.0/doc/controllers/calls-participants.md)
* [Chat](https://www.github.com/sohail2721/slackapi-dotnet-sdk/tree/1.0.0/doc/controllers/chat.md)
* [Chat Scheduled Messages](https://www.github.com/sohail2721/slackapi-dotnet-sdk/tree/1.0.0/doc/controllers/chat-scheduled-messages.md)
* [Conversations](https://www.github.com/sohail2721/slackapi-dotnet-sdk/tree/1.0.0/doc/controllers/conversations.md)
* [Dialog](https://www.github.com/sohail2721/slackapi-dotnet-sdk/tree/1.0.0/doc/controllers/dialog.md)
* [Dnd](https://www.github.com/sohail2721/slackapi-dotnet-sdk/tree/1.0.0/doc/controllers/dnd.md)
* [Emoji](https://www.github.com/sohail2721/slackapi-dotnet-sdk/tree/1.0.0/doc/controllers/emoji.md)
* [Files Comments](https://www.github.com/sohail2721/slackapi-dotnet-sdk/tree/1.0.0/doc/controllers/files-comments.md)
* [Files](https://www.github.com/sohail2721/slackapi-dotnet-sdk/tree/1.0.0/doc/controllers/files.md)
* [Files Remote](https://www.github.com/sohail2721/slackapi-dotnet-sdk/tree/1.0.0/doc/controllers/files-remote.md)
* [Migration](https://www.github.com/sohail2721/slackapi-dotnet-sdk/tree/1.0.0/doc/controllers/migration.md)
* [Oauth](https://www.github.com/sohail2721/slackapi-dotnet-sdk/tree/1.0.0/doc/controllers/oauth.md)
* [Oauth V 2](https://www.github.com/sohail2721/slackapi-dotnet-sdk/tree/1.0.0/doc/controllers/oauth-v-2.md)
* [Pins](https://www.github.com/sohail2721/slackapi-dotnet-sdk/tree/1.0.0/doc/controllers/pins.md)
* [Reactions](https://www.github.com/sohail2721/slackapi-dotnet-sdk/tree/1.0.0/doc/controllers/reactions.md)
* [Reminders](https://www.github.com/sohail2721/slackapi-dotnet-sdk/tree/1.0.0/doc/controllers/reminders.md)
* [Rtm](https://www.github.com/sohail2721/slackapi-dotnet-sdk/tree/1.0.0/doc/controllers/rtm.md)
* [Search](https://www.github.com/sohail2721/slackapi-dotnet-sdk/tree/1.0.0/doc/controllers/search.md)
* [Stars](https://www.github.com/sohail2721/slackapi-dotnet-sdk/tree/1.0.0/doc/controllers/stars.md)
* [Team](https://www.github.com/sohail2721/slackapi-dotnet-sdk/tree/1.0.0/doc/controllers/team.md)
* [Team Profile](https://www.github.com/sohail2721/slackapi-dotnet-sdk/tree/1.0.0/doc/controllers/team-profile.md)
* [Usergroups](https://www.github.com/sohail2721/slackapi-dotnet-sdk/tree/1.0.0/doc/controllers/usergroups.md)
* [Usergroups Users](https://www.github.com/sohail2721/slackapi-dotnet-sdk/tree/1.0.0/doc/controllers/usergroups-users.md)
* [Users](https://www.github.com/sohail2721/slackapi-dotnet-sdk/tree/1.0.0/doc/controllers/users.md)
* [Users Profile](https://www.github.com/sohail2721/slackapi-dotnet-sdk/tree/1.0.0/doc/controllers/users-profile.md)
* [Views](https://www.github.com/sohail2721/slackapi-dotnet-sdk/tree/1.0.0/doc/controllers/views.md)
* [Workflows](https://www.github.com/sohail2721/slackapi-dotnet-sdk/tree/1.0.0/doc/controllers/workflows.md)

## SDK Infrastructure

### Configuration

* [Configuration-Based Initialization](https://www.github.com/sohail2721/slackapi-dotnet-sdk/tree/1.0.0/doc/configuration-based-initialization.md)
* [HttpClientConfiguration](https://www.github.com/sohail2721/slackapi-dotnet-sdk/tree/1.0.0/doc/http-client-configuration.md)
* [HttpClientConfigurationBuilder](https://www.github.com/sohail2721/slackapi-dotnet-sdk/tree/1.0.0/doc/http-client-configuration-builder.md)
* [LogBuilder](https://www.github.com/sohail2721/slackapi-dotnet-sdk/tree/1.0.0/doc/log-builder.md)
* [LogRequestBuilder](https://www.github.com/sohail2721/slackapi-dotnet-sdk/tree/1.0.0/doc/log-request-builder.md)
* [LogResponseBuilder](https://www.github.com/sohail2721/slackapi-dotnet-sdk/tree/1.0.0/doc/log-response-builder.md)
* [ProxyConfigurationBuilder](https://www.github.com/sohail2721/slackapi-dotnet-sdk/tree/1.0.0/doc/proxy-configuration-builder.md)

### HTTP

* [HttpCallback](https://www.github.com/sohail2721/slackapi-dotnet-sdk/tree/1.0.0/doc/http-callback.md)
* [HttpContext](https://www.github.com/sohail2721/slackapi-dotnet-sdk/tree/1.0.0/doc/http-context.md)
* [HttpRequest](https://www.github.com/sohail2721/slackapi-dotnet-sdk/tree/1.0.0/doc/http-request.md)
* [HttpResponse](https://www.github.com/sohail2721/slackapi-dotnet-sdk/tree/1.0.0/doc/http-response.md)
* [HttpStringResponse](https://www.github.com/sohail2721/slackapi-dotnet-sdk/tree/1.0.0/doc/http-string-response.md)

### Utilities

* [ApiException](https://www.github.com/sohail2721/slackapi-dotnet-sdk/tree/1.0.0/doc/api-exception.md)
* [ApiResponse](https://www.github.com/sohail2721/slackapi-dotnet-sdk/tree/1.0.0/doc/api-response.md)
* [ApiHelper](https://www.github.com/sohail2721/slackapi-dotnet-sdk/tree/1.0.0/doc/api-helper.md)

