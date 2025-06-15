# Google Gemini API Key Setup Guide

## Creating a Google Gemini API Key

### Step 1: Set Up Google Cloud Project
1. Visit [Google Cloud Console](https://console.cloud.google.com)
2. Create a new project or select an existing one
3. Enable billing for your project
   - Note: Google Cloud requires a billing account, but Gemini API has a free tier

### Step 2: Enable Gemini API
1. In the Google Cloud Console, go to "APIs & Services" > "Library"
2. Search for "Gemini API"
3. Click "Enable" to activate the API for your project

### Step 3: Generate API Key
1. Go to "APIs & Services" > "Credentials"
2. Click "Create Credentials" > "API Key"
3. Copy the generated API key
4. (Optional) Restrict the API key to Gemini API only for security

## Configure API Key on a Drupal Website

### Step 1: Install Required Modules
```bash
lando drush en key key_value_field -y
```

### Step 2: Configure Key Module
1. Go to `/admin/config/system/keys` in your Drupal site
2. Click "Add key"
3. Fill in the following details:
   - Key name: `gemini_api_key`
   - Key type: `Authentication`
   - Key provider: `File`
   - Key value: Paste your Gemini API key
4. Click "Save"

### Step 3: Configure AI Module Settings
1. Go to `/admin/config/ai/settings`
2. Select "Gemini" as the AI provider
3. In the API Key field, select the key you created
4. Save the configuration

### Step 4: Test the Configuration
1. Clear the cache:
```bash
lando drush cr
```
2. Try a test AI operation to verify the setup

## Security Best Practices
- Never commit your API key to version control
- Use environment variables or the Key module for secure storage
- Regularly rotate your API keys
- Set up API key restrictions in Google Cloud Console
- Monitor your API usage in Google Cloud Console
- Set up budget alerts to avoid unexpected charges

## Troubleshooting
If you encounter issues:
1. Verify the API key is correctly stored in the Key module
2. Check the Drupal logs for any API-related errors
3. Ensure your Google Cloud project has the Gemini API enabled
4. Verify your API key hasn't been restricted or revoked
5. Check your Google Cloud Console for any quota or billing issues

## Free Tier and Pricing
- Gemini API offers a free tier with generous limits
- Monitor your usage in Google Cloud Console
- Set up budget alerts to avoid unexpected charges
- Review [Gemini API pricing](https://cloud.google.com/vertex-ai/pricing) for current rates
