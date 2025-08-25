# SCIM Configuration

The Platform adheres to the SCIM 2.0 specification. It is used for the automatic provisioning, synchronization, and deprovisioning of users. The Platform supports both the `/Users` and `/Groups` endpoints.

* The **Users** endpoint is used to create, update, and delete users in the Strong Network Platform.
* The **Groups** endpoint is used to create, update, and delete groups in the Strong Network Platform. You can then map these groups to organization(s) and/or project(s) within the Strong Network Platform.

## Configure the SCIM Provider:

A token is required to authorize requests between your SCIM provider of choice and the Strong Network Platform. As an admin, you can obtain the token at:

**System Configuration → Identity Providers → SCIM Configuration**

`https://example.strong.network/system_configuration/identity_providers/scim`

![SCIM Platform](../assets/images/scim/scim_1.png)

Please ensure that your SCIM provider of choice—such as Microsoft Entra, Okta, or any other SCIM 2.0-compliant provider—includes this token in all API requests, using the following authorization header format:

`Authorization: Bearer <token>`

### Using Okta

To use Okta, you will need to set these two fields:

* **SCIM connector base URL:** `https://example.strong.network/scim`
* **Unique identifier field for users:** `userName`

It will look similar to:
![SCIM Okta Config](../assets/images/scim/scim_okta_1.png)

Under users you can enable the following options, as desired:
![SCIM Okta Config Users](../assets/images/scim/scim_okta_2.png)

### Using PingOne

To use PingOne, you will need to set the following fields:

* **SCIM base URL:** `https://example.strong.network/scim`
* **User Filter Expression**: Modify "username" by "userName" as well as "Eq" to "eq"

When configuring it should look like:
![PingOne Config](../assets/images/scim/scim_pingone_3.png)

When configured the result should be like:
![PingOne Configured](../assets/images/scim/scim_pingone_1.png)
![PingOne Configured 2](../assets/images/scim/scim_pingone_2.png)

### Using OneLogin
To use OneLogin, you will need to set the following fields:

* **SCIM base URL:** `https://example.strong.network/scim`
* **scimusername**: Set its value to Email

The configuration should look like:
![OneLogin Configured](../assets/images/scim/scim_onelogin_1.png)
![OneLogin Configured 2](../assets/images/scim/scim_onelogin_2.png)

The parameters section should look like:
![OneLogin Configured 3](../assets/images/scim/scim_onelogin_3.png)


### Using Xecurify (miniOrange)
To use Xecurify, you will need to set the following fields:
* **SCIM Base URL:** `https://example.strong.network/scim`
* **userName**: Set its value to E-Mail Address


The configuration should look like:
![Xecurify Configured](../assets/images/scim/scim_xecurify_1.png)
![Xecurify Configured 2](../assets/images/scim/scim_xecurify_2.png)

## Configure the Strong Network Platform:

No additional configuration is needed on the Strong Network Platform. SCIM is enabled by default.

You can renew the token at any time. Please note that renewing the token will invalidate any previously issued tokens.

![SCIM Renewal](../assets/images/scim/scim_2.png)
