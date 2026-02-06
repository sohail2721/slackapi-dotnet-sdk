
# OAuth 2 Authorization Code Grant



Documentation for accessing and setting credentials for slackAuth.

## Auth Credentials

| Name | Type | Description | Setter | Getter |
|  --- | --- | --- | --- | --- |
| OAuthClientId | `string` | OAuth 2 Client ID | `OauthClientId` | `OauthClientId` |
| OAuthClientSecret | `string` | OAuth 2 Client Secret | `OauthClientSecret` | `OauthClientSecret` |
| OAuthRedirectUri | `string` | OAuth 2 Redirection endpoint or Callback Uri | `OauthRedirectUri` | `OauthRedirectUri` |
| OAuthToken | `Models.OauthToken` | Object for storing information about the OAuth token | `OauthToken` | `OauthToken` |
| OAuthScopes | `List<Models.OauthScope>` | List of scopes that apply to the OAuth token | `OauthScopes` | `OauthScopes` |



**Note:** Auth credentials can be set using `AuthorizationCodeAuth` in the client builder and accessed through `AuthorizationCodeAuth` method in the client instance.

## Usage Example

### 1\. Client Initialization

You must initialize the client with *OAuth 2.0 Authorization Code Grant* credentials as shown in the following code snippet.

```csharp
using SlackWebApi.Standard;
using SlackWebApi.Standard.Authentication;

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
    .Build();
```



Your application must obtain user authorization before it can execute an endpoint call in case this SDK chooses to use *OAuth 2.0 Authorization Code Grant*. This authorization includes the following steps

### 2\. Obtain user consent

To obtain user's consent, you must redirect the user to the authorization page.The `BuildAuthorizationUrl()` method creates the URL to the authorization page. You must have initialized the client with scopes for which you need permission to access.

```csharp
string authUrl = await client.AuthorizationCodeAuth.BuildAuthorizationUrl();
```

### 3\. Handle the OAuth server response

Once the user responds to the consent request, the OAuth 2.0 server responds to your application's access request by redirecting the user to the redirect URI specified set in `Configuration`.

If the user approves the request, the authorization code will be sent as the `code` query string:

```
https://example.com/oauth/callback?code=XXXXXXXXXXXXXXXXXXXXXXXXX
```

If the user does not approve the request, the response contains an `error` query string:

```
https://example.com/oauth/callback?error=access_denied
```

### 4\. Authorize the client using the code

After the server receives the code, it can exchange this for an *access token*. The access token is an object containing information for authorizing client requests and refreshing the token itself.

```csharp
var authManager = client.AuthorizationCodeAuth;

try
{
    OauthToken token = authManager.FetchToken(authorizationCode);
    // re-instantiate the client with OAuth token
    client = client.ToBuilder()
        .AuthorizationCodeAuth(
            client.AuthorizationCodeAuthModel.ToBuilder()
                .OauthToken(token)
                .Build())
        .Build();
}
catch (ApiException e)
{
    // TODO Handle exception
}
```

### Scopes

Scopes enable your application to only request access to the resources it needs while enabling users to control the amount of access they grant to your application. Available scopes are defined in the [`OauthScope`](../../doc/models/oauth-scope.md) enumeration.

| Scope Name | Description |
|  --- | --- |
| `ADMIN` | admin |
| `ADMIN.APPSREAD` | admin.apps:read |
| `ADMIN.APPSWRITE` | admin.apps:write |
| `ADMIN.CONVERSATIONSREAD` | admin.conversations:read |
| `ADMIN.CONVERSATIONSWRITE` | admin.conversations:write |
| `ADMIN.INVITESREAD` | admin.invites:read |
| `ADMIN.INVITESWRITE` | admin.invites:write |
| `ADMIN.TEAMSREAD` | admin.teams:read |
| `ADMIN.TEAMSWRITE` | admin.teams:write |
| `ADMIN.USERGROUPSREAD` | admin.usergroups:read |
| `ADMIN.USERGROUPSWRITE` | admin.usergroups:write |
| `ADMIN.USERSREAD` | admin.users:read |
| `ADMIN.USERSWRITE` | admin.users:write |
| `AUTHORIZATIONSREAD` | authorizations:read |
| `BOT` | Bot user scope |
| `CALLSREAD` | calls:read |
| `CALLSWRITE` | calls:write |
| `CHANNELSHISTORY` | channels:history |
| `CHANNELSMANAGE` | channels:manage |
| `CHANNELSREAD` | channels:read |
| `CHANNELSWRITE` | channels:write |
| `CHATWRITE` | chat:write |
| `CHATWRITEBOT` | Author messages as a bot |
| `CHATWRITEUSER` | Author messages as a user |
| `CONVERSATIONSHISTORY` | conversations:history |
| `CONVERSATIONSREAD` | conversations:read |
| `CONVERSATIONSWRITE` | conversations:write |
| `DNDREAD` | dnd:read |
| `DNDWRITE` | dnd:write |
| `EMOJIREAD` | emoji:read |
| `FILESREAD` | files:read |
| `FILESWRITEUSER` | files:write:user |
| `GROUPSHISTORY` | groups:history |
| `GROUPSREAD` | groups:read |
| `GROUPSWRITE` | groups:write |
| `IDENTITY.BASIC` | identity.basic |
| `IMHISTORY` | im:history |
| `IMREAD` | im:read |
| `IMWRITE` | im:write |
| `LINKSWRITE` | links:write |
| `MPIMHISTORY` | mpim:history |
| `MPIMREAD` | mpim:read |
| `MPIMWRITE` | mpim:write |
| `NONE` | No scope required |
| `PINSREAD` | pins:read |
| `PINSWRITE` | pins:write |
| `REACTIONSREAD` | reactions:read |
| `REACTIONSWRITE` | reactions:write |
| `REMINDERSREAD` | reminders:read |
| `REMINDERSWRITE` | reminders:write |
| `REMOTE_FILESREAD` | remote_files:read |
| `REMOTE_FILESSHARE` | remote_files:share |
| `REMOTE_FILESWRITE` | remote_files:write |
| `RTMSTREAM` | rtm:stream |
| `SEARCHREAD` | search:read |
| `STARSREAD` | stars:read |
| `STARSWRITE` | stars:write |
| `TEAMREAD` | team:read |
| `TOKENS.BASIC` | tokens.basic |
| `USERGROUPSREAD` | usergroups:read |
| `USERGROUPSWRITE` | usergroups:write |
| `USERS.PROFILEREAD` | users.profile:read |
| `USERS.PROFILEWRITE` | users.profile:write |
| `USERSREAD` | users:read |
| `USERSREAD.EMAIL` | users:read.email |
| `USERSWRITE` | users:write |
| `WORKFLOW.STEPSEXECUTE` | workflow.steps:execute |

### Refreshing the token

An access token may expire after sometime. To extend its lifetime, you must refresh the token.

```csharp
if (authManager.IsTokenExpired())
{
    try
    {
        OauthToken token = authManager.RefreshToken();
        // re-instantiate the client with OAuth token
        client = client.ToBuilder()
            .AuthorizationCodeAuth(
                client.AuthorizationCodeAuthModel.ToBuilder()
                    .OauthToken(token)
                    .Build())
            .Build();
    }
    catch (ApiException e)
    {
        // TODO Handle exception
    }
}
```

If a token expires, an exception will be thrown before the next endpoint call requiring authentication.

### Storing an access token for reuse

It is recommended that you store the access token for reuse.

```csharp
// store token
SaveTokenToDatabase(client.AuthorizationCodeAuth.OauthToken);
```

### Creating a client from a stored token

To authorize a client using a stored access token, just set the access token in Configuration along with the other configuration parameters before creating the client:

```csharp
// load token later
OAuthToken token = LoadTokenFromDatabase();

// re-instantiate the client with OAuth token
SlackWebApiClient client = client.ToBuilder()
    .AuthorizationCodeAuth(
        client.AuthorizationCodeAuthModel.ToBuilder()
            .OauthToken(token)
            .Build())
    .Build();
```

### Complete example



```csharp
using SlackWebApi.Standard;
using SlackWebApi.Standard.Models;
using SlackWebApi.Standard.Exceptions;
using SlackWebApi.Standard.Authentication;
using System.Collections.Generic;
namespace OAuthTestApplication
{
    class Program
    {
        static void Main(string[] args)
        {
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
                .Build();
            try
            {
                OauthToken token = LoadTokenFromDatabase();

                // Set the token if it is not set before
                if (token == null)
                {
                    var authManager = client.AuthorizationCodeAuth;
                    string authUrl = await authManager.BuildAuthorizationUrl();
                    string authorizationCode = GetAuthorizationCode(authUrl);
                    token = authManager.FetchToken(authorizationCode);
                }

                SaveTokenToDatabase(token);
                // re-instantiate the client with OAuth token
                client = client.ToBuilder()
                    .AuthorizationCodeAuth(
                        client.AuthorizationCodeAuthModel.ToBuilder()
                            .OauthToken(token)
                            .Build())
                    .Build();
            }
            catch (OAuthProviderException e)
            {
                // TODO Handle exception
            }
        }

        private static string GetAuthorizationCode(string authUrl)
        {
            // TODO Open the given auth URL, give access and return authorization code from redirect URL
            return string.Empty;
        }

        private static void SaveTokenToDatabase(OAuthToken token)
        {
            //Save token here
        }

        private static OAuthToken LoadTokenFromDatabase()
        {
            OAuthToken token = null;
            //token = Get token here
            return token;
        }
    }
}

// the client is now authorized and you can use controllers to make endpoint calls
```


