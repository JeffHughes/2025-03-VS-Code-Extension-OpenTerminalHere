# Publishing to VS Code Marketplace

## Step 1: Create a Personal Access Token (PAT)

1. Go to https://dev.azure.com/
2. Sign in with your Microsoft account (create one if you don't have one)
3. Click on your profile icon in the top right corner
4. Select "Personal access tokens"
5. Click "New Token"
6. Name: "VS Code Marketplace Publishing"
7. Organization: "All accessible organizations"
8. Expiration: Set as needed (e.g., 1 year)
9. Scopes: Select "Custom defined" and then check "Marketplace > Manage"
10. Click "Create"
11. **IMPORTANT**: Copy the token immediately and save it securely. You won't be able to see it again.

## Step 2: Login to vsce

Run the following command in your terminal:

```bash
npx vsce login jeff-hughes
```

When prompted, paste your Personal Access Token.

## Step 3: Publish the Extension

Run the following command to publish your extension:

```bash
npx vsce publish
```

This will publish the extension to the VS Code Marketplace under the publisher name "jeff-hughes".

## Step 4: Verify Publication

1. Go to https://marketplace.visualstudio.com/
2. Search for "Open Terminal Here"
3. You should see your extension listed

## Updating the Extension

To update your extension in the future:

1. Make your changes
2. Update the version number in package.json
3. Run `npx vsce publish` again

## Managing Your Extension

You can manage your published extensions at:
https://marketplace.visualstudio.com/manage
