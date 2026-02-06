
# Client Class Documentation

The following parameters are configurable for the API Client:

| Parameter | Type | Description |
|  --- | --- | --- |
| Environment | [`Environment`](../README.md#environments) | The API environment. <br> **Default: `Environment.Production`** |
| Timeout | `TimeSpan` | Http client timeout.<br>*Default*: `TimeSpan.FromSeconds(30)` |
| HttpClientConfiguration | [`Action<HttpClientConfiguration.Builder>`](../doc/http-client-configuration-builder.md) | Action delegate that configures the HTTP client by using the HttpClientConfiguration.Builder for customizing API call settings.<br>*Default*: `new HttpClient()` |
| LogBuilder | [`LogBuilder`](../doc/log-builder.md) | Represents the logging configuration builder for API calls |
| AuthorizationCodeAuth | [`AuthorizationCodeAuth`](auth/oauth-2-authorization-code-grant.md) | The Credentials Setter for OAuth 2 Authorization Code Grant |

The API client can be initialized as follows:

## Code-Based Initialization

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

## Configuration-Based Initialization

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

See the [Configuration-Based Initialization](../doc/configuration-based-initialization.md) section for details.

## Slack Web APIClient Class

The gateway for the SDK. This class acts as a factory for the Controllers and also holds the configuration of the SDK.

### Controllers

| Name | Description |
|  --- | --- |
| AdminAppsController | Gets AdminAppsController controller. |
| AdminAppsApprovedController | Gets AdminAppsApprovedController controller. |
| AdminAppsRequestsController | Gets AdminAppsRequestsController controller. |
| AdminAppsRestrictedController | Gets AdminAppsRestrictedController controller. |
| AdminConversationsController | Gets AdminConversationsController controller. |
| AdminConversationsEkmController | Gets AdminConversationsEkmController controller. |
| AdminConversationsRestrictAccessController | Gets AdminConversationsRestrictAccessController controller. |
| AdminEmojiController | Gets AdminEmojiController controller. |
| AdminInviteRequestsController | Gets AdminInviteRequestsController controller. |
| AdminInviteRequestsApprovedController | Gets AdminInviteRequestsApprovedController controller. |
| AdminInviteRequestsDeniedController | Gets AdminInviteRequestsDeniedController controller. |
| AdminTeamsAdminsController | Gets AdminTeamsAdminsController controller. |
| AdminTeamsController | Gets AdminTeamsController controller. |
| AdminTeamsOwnersController | Gets AdminTeamsOwnersController controller. |
| AdminTeamsSettingsController | Gets AdminTeamsSettingsController controller. |
| AdminUsergroupsController | Gets AdminUsergroupsController controller. |
| AdminUsersController | Gets AdminUsersController controller. |
| AdminUsersSessionController | Gets AdminUsersSessionController controller. |
| ApiController | Gets ApiController controller. |
| AppsEventAuthorizationsController | Gets AppsEventAuthorizationsController controller. |
| AppsPermissionsController | Gets AppsPermissionsController controller. |
| AppsPermissionsResourcesController | Gets AppsPermissionsResourcesController controller. |
| AppsPermissionsScopesController | Gets AppsPermissionsScopesController controller. |
| AppsPermissionsUsersController | Gets AppsPermissionsUsersController controller. |
| AppsController | Gets AppsController controller. |
| AuthController | Gets AuthController controller. |
| BotsController | Gets BotsController controller. |
| CallsController | Gets CallsController controller. |
| CallsParticipantsController | Gets CallsParticipantsController controller. |
| ChatController | Gets ChatController controller. |
| ChatScheduledMessagesController | Gets ChatScheduledMessagesController controller. |
| ConversationsController | Gets ConversationsController controller. |
| DialogController | Gets DialogController controller. |
| DndController | Gets DndController controller. |
| EmojiController | Gets EmojiController controller. |
| FilesCommentsController | Gets FilesCommentsController controller. |
| FilesController | Gets FilesController controller. |
| FilesRemoteController | Gets FilesRemoteController controller. |
| MigrationController | Gets MigrationController controller. |
| OauthController | Gets OauthController controller. |
| OauthV2Controller | Gets OauthV2Controller controller. |
| PinsController | Gets PinsController controller. |
| ReactionsController | Gets ReactionsController controller. |
| RemindersController | Gets RemindersController controller. |
| RtmController | Gets RtmController controller. |
| SearchController | Gets SearchController controller. |
| StarsController | Gets StarsController controller. |
| TeamController | Gets TeamController controller. |
| TeamProfileController | Gets TeamProfileController controller. |
| UsergroupsController | Gets UsergroupsController controller. |
| UsergroupsUsersController | Gets UsergroupsUsersController controller. |
| UsersController | Gets UsersController controller. |
| UsersProfileController | Gets UsersProfileController controller. |
| ViewsController | Gets ViewsController controller. |
| WorkflowsController | Gets WorkflowsController controller. |
| OauthAuthorizationController | Gets OauthAuthorizationController controller. |

### Properties

| Name | Description | Type |
|  --- | --- | --- |
| HttpClientConfiguration | Gets the configuration of the Http Client associated with this client. | [`IHttpClientConfiguration`](../doc/http-client-configuration.md) |
| Timeout | Http client timeout. | `TimeSpan` |
| Environment | Current API environment. | `Environment` |
| AuthorizationCodeAuth | Gets the credentials to use with AuthorizationCodeAuth. | [`IAuthorizationCodeAuth`](auth/oauth-2-authorization-code-grant.md) |

### Methods

| Name | Description | Return Type |
|  --- | --- | --- |
| `GetBaseUri(Server alias = Server.Default)` | Gets the URL for a particular alias in the current environment and appends it with template parameters. | `string` |
| `ToBuilder()` | Creates an object of the Slack Web APIClient using the values provided for the builder. | `Builder` |

## Slack Web APIClient Builder Class

Class to build instances of Slack Web APIClient.

### Methods

| Name | Description | Return Type |
|  --- | --- | --- |
| `HttpClientConfiguration(Action<`[`HttpClientConfiguration.Builder`](../doc/http-client-configuration-builder.md)`> action)` | Gets the configuration of the Http Client associated with this client. | `Builder` |
| `Timeout(TimeSpan timeout)` | Http client timeout. | `Builder` |
| `Environment(Environment environment)` | Current API environment. | `Builder` |
| `AuthorizationCodeAuth(Action<AuthorizationCodeAuthModel.Builder> action)` | Sets credentials for AuthorizationCodeAuth. | `Builder` |

