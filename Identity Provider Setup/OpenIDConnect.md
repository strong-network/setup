# OpenID Connect Configuration as Identity Provider (OIDC)

This platform supports integration with OpenID Connect for logging in.

## Registering the Application

- Go to the OpenID Provider's Developer Portal.
- Navigate to the Applications or Clients section.
- Click on “Create New Application” or equivalent. Set the following:
  - **App Name**: Choose a name that will be displayed to users logging in.
  - **Application Type**: Select “Web Application”.
  - **Redirect URIs**: Add the following URI to handle login redirects: `https://example.com/oauth/callback`
  - **Logout Redirect URI**: Add the following URI to handle logout redirects: `https://example.com/auth/logout`
- Save the application.

Note the Client ID and Client Secret generated during this process. These will be required for platform configuration.

## Configuring Scopes and Claims

Under the Scopes or Permissions section of your application, ensure the following scopes are included:

- `openid`
- `email`
- `profile`
- Any additional scopes your platform requires.

Configure claims if necessary. Common claims include:

- `sub`: Unique identifier for the user.
- `email`: User's email address.
- `name`: Full name of the user.
- `preferred_username`: Username or handle.

## Enabling Single Logout (SLO)

To enable Single Logout (SLO) for OpenID Connect:

Navigate to the Advanced Settings or Logout Configuration section.

Enable Single Logout if supported by the provider.

Add the Logout Redirect URI configured earlier:

`https://example.com/auth/logout`

Optionally, add the following claims to the ID token:

- `sid`: Session identifier.
- `logout_hint`: Provides context for logging out.
