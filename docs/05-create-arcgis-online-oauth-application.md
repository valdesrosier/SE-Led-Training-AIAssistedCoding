# Create an OAuth application in ArcGIS Online

[Back to the pre-work overview](../README.md)

Use these steps to create OAuth 2.0 credentials for a browser application that signs users in with their ArcGIS accounts.

## Before you begin

You need:

- An ArcGIS Online account that can create content.
- The redirect URL used by your application after sign-in. For the JavaScript exercise in this repository, use `https://localhost:*` so the local development server can use any available port.

The redirect URL must match the URL used by your application. In `https://localhost:*`, the `*` matches whichever local port the development server uses. Production redirect URLs should specify the exact protocol, hostname, port, path, and trailing slash.

## Step 1: Open the developer credentials workflow

1. Sign in to your ArcGIS Online organization.
2. Select **Content** in the top navigation.
3. On **My content**, select **New item**.
4. In the New item panel, select **Developer credentials**.

![The ArcGIS Online New item panel with Developer credentials available](assets/arcgis-oauth-01-new-item.png)

## Step 2: Select the OAuth credential type

1. Select **OAuth 2.0 credentials - For user authentication**.
2. Select **Next**.

This option is intended for applications that require users to sign in with an ArcGIS account. Do not select **For app authentication** for a browser-based user sign-in flow.

![OAuth 2.0 credentials for user authentication in the credential type table](assets/arcgis-oauth-02-credential-type.png)

## Step 3: Configure the redirect URL

1. Enter the redirect URL for your application. For this workshop, use `https://localhost:*`.
2. Under **Application environment**, select **Browser**.
3. Select **Next**.

![Redirect URL and Browser application environment settings](assets/arcgis-oauth-03-settings.png)

> [!NOTE]
> Select **Add** only when you need another redirect URL. If an empty redirect row appears, remove it with the delete button before continuing.

For a deployed application, add its production callback URL as a separate redirect URL. Avoid broad or unrelated URLs.

## Step 4: Enter the item details

1. Enter a descriptive **Title**, such as `My Project OAuth App`.
2. Add at least one **Tag**, such as `OAuth`.
3. Add a short **Summary** describing which application uses the credentials.
4. Select **Next**.

## Step 5: Review and create the credentials

Confirm that the review screen shows:

- **Credential type:** OAuth 2.0 credentials for user authentication
- **Redirect URL:** the exact address used by your application

Select **Create**.

![OAuth credentials review screen before creation](assets/arcgis-oauth-05-review.png)

## Step 6: Return later to copy the client ID

After ArcGIS Online opens the new item's Overview page, confirm that the **Credentials** section displays a **Client ID**. Do not copy it yet. You will return to this step after you create an application and are ready to configure OAuth.

When the application exercise asks you to configure OAuth:

1. Open the credentials item's Overview page.
2. Find the **Credentials** section.
3. Copy the **Client ID**.
4. Add the client ID to the configuration location expected by your application, such as an `.env.local` file.

The client ID identifies the OAuth application and is safe to use in browser code. It is not a password.

> [!NOTE]
> It is safe to share the **Client ID** with your coding assistant. The assistant can use it to configure and help build authentication features in your application.

> [!IMPORTANT]
> Do not copy, share, commit, or place the **Client Secret** or **Temporary Token** in browser code. A browser application using OAuth user authentication should use the client ID, not the client secret.

## Update the redirect URL later

Open the credentials item, select **Settings**, and find **Application > Redirect URLs**. Add the new callback URL and remove URLs that are no longer used.

For more detail, see Esri's [OAuth 2.0 credentials for user authentication](https://developers.arcgis.com/documentation/security-and-authentication/user-authentication/oauth-credentials-user/).
