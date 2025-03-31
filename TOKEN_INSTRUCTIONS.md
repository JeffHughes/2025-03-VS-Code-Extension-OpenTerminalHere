# Creating a Personal Access Token for VS Code Marketplace

## Detailed Permission Requirements

When creating your Personal Access Token (PAT) in Azure DevOps, you need to include the following specific permissions:

1. **Marketplace**
   - Marketplace (Read)
   - Marketplace (Publish)
   - Marketplace (Manage)

2. **Member Entitlement Management**
   - Member Entitlement Management (Read)

3. **Organization**
   - Organization (Read)

## Step-by-Step Instructions

1. Go to https://dev.azure.com/

2. Sign in with your Microsoft account

3. Click on your profile icon in the top right corner

4. Select "Personal access tokens"

5. Click "New Token"

6. Fill in the details:
   - Name: "VS Code Marketplace Publishing"
   - Organization: "All accessible organizations"
   - Expiration: Set as needed (e.g., 1 year)

7. For Scopes, select "Custom defined" and then check the following:
   - Marketplace > Check ALL options (Read, Publish, Manage)
   - Member Entitlement Management > Read
   - Organization > Read

8. Click "Create"

9. Copy the token immediately and save it securely

## Using the Token

Once you have the token with the correct permissions, you can publish directly using:

```bash
npx vsce publish -p <your-token>
```

Or try logging in again:

```bash
npx vsce login jeff-hughes
```

## Alternative: Create a Publisher First

If you're still having issues, you might need to create the publisher first:

### The Issue

The error message indicates you're trying to access a publisher that either doesn't exist yet or you don't have permissions for:

```
Error: Access Denied: 802d6ca2-2a8a-6a55-a5dd-6db553a029be needs the following permission(s) on the resource /jeff-hughes to perform this action: View user permissions on a resource
```

### Solution: Create the Publisher First

1. Go to https://marketplace.visualstudio.com/manage/publishers/
2. Sign in with your Microsoft account
3. Click "New Publisher"
4. Fill in the details:
   - Publisher ID: `jeff-hughes` (must match what's in your package.json)
   - Display Name: Your name or company name
   - Description: Brief description of your publishing entity
5. Complete the registration process

### Create a New PAT with Full Permissions

After creating the publisher, create a new PAT with these permissions:

1. Go to https://dev.azure.com/
2. Click your profile icon → Personal access tokens
3. Click "New Token"
4. Fill in:
   - Name: "VS Code Marketplace Full Access"
   - Organization: "All accessible organizations"
   - Expiration: Set as needed
   - Scopes: Select "Full access"
5. Click "Create"
6. Copy the token

### Alternative: Direct Publishing

If you still have issues with login, you can publish directly:

```bash
npx vsce publish -p <your-token>
```

### If All Else Fails

If you continue to have issues, try these steps:

1. Make sure your Microsoft account email matches between Azure DevOps and the Marketplace
2. Try creating a completely new PAT with full access permissions
3. Verify the publisher name in package.json matches exactly what you created in the Marketplace
4. Try publishing from the web interface at https://marketplace.visualstudio.com/manage/publishers/
