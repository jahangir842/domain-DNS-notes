In Cloudflare, API tokens are used to authenticate and authorize API requests to manage your Cloudflare account and services. They provide a secure way to interact with Cloudflare's APIs without using your account's global API key.

Here's a quick overview of the different types of API tokens you might encounter in Cloudflare:

1. **Global API Key**: This key provides full access to your Cloudflare account and is used for legacy API v1. It should be kept secret and is not recommended for use in most scenarios due to its broad access level.

2. **API Tokens**: These are more secure and flexible than the global API key. You can create API tokens with specific permissions for different actions and resources. They are used with Cloudflare’s API v4 and offer fine-grained access control.

### Creating an API Token

To create an API token in Cloudflare:

1. **Log in to your Cloudflare account**.
2. **Go to the API Tokens page**:
   - Navigate to the **"My Profile"** section from the dashboard.
   - Click on **"API Tokens"** in the sidebar.
3. **Create a new token**:
   - Click **"Create Token"**.
   - You can either use a predefined template for common tasks or create a custom token with specific permissions.
4. **Set permissions**:
   - Choose the permissions you need (e.g., read, write, or edit) and apply them to the desired resources (e.g., DNS settings, zones).
5. **Generate the token**:
   - Follow the prompts to complete the creation of your API token.
   - Make sure to copy and store the token securely as it will not be retrievable once you leave the page.

### Example Use

If you want to manage DNS records using the Cloudflare API, you might create an API token with permissions for the DNS zone you want to control. Here’s how you would use it in a `curl` command:

```bash
curl -X GET "https://api.cloudflare.com/client/v4/zones/YOUR_ZONE_ID/dns_records" \
-H "Authorization: Bearer YOUR_API_TOKEN" \
-H "Content-Type: application/json"
```

In this example:
- Replace `YOUR_ZONE_ID` with your Cloudflare zone ID.
- Replace `YOUR_API_TOKEN` with the API token you generated.

This command retrieves DNS records for the specified zone using the API token for authentication.
