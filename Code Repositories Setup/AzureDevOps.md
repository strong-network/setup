# Azure Dev Ops integration as Code Repository Provider

Follow these steps to create an OAuth App in Azure DevOps to connect it to the platform.

- Using an Azure DevOps account, go to the following link:
   [Register an application](https://app.vsaex.visualstudio.com/app/register)

- Click on the "Add consumer" button and set the following fields:
   - **Company Name:** Your company’s name.
   - **Application Name:** The name you want to give to the application. It will be public.
   - **Application Website:** Set to `https://example.com/oauth/apps/callback` (replace `example.com` with the proper domain name).
   - **Authorization Callback URL:** Set to `https://example.com/oauth/apps/callback` (replace `example.com` with the proper domain name). This URL can be found in the admin panel of the Strong Network platform.
   - **Authorized Scopes:** `Code (read and write)` and `Project and team (read)`.

- Once done, click the "Create Application" button. You will be presented with the Client ID (called App ID) and the Secret (called Client Secret) after clicking the "Show" button. Enter these fields in the Admin configuration of the Strong Network platform.

   - [Register an application](https://app.vsaex.visualstudio.com/app/register)
   - `https://example.com/oauth/apps/callback`

- Specify the Azure Organization name. This application can only access repositories under this specific organization. To access repositories from different organizations, create multiple Azure DevOps Code Repository Applications, each with its corresponding organization name. You may use the same Client ID and Secret across all of them.
![Azure Dev Ops](../assets/images/azure_devops_add.png)

Paste Client ID, App Secret and Organization name from steps above: 

![Azure Dev Ops 2](../assets/images/azure_devops_add_2.png)