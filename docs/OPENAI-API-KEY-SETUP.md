# OpenAI API Key Setup Guide

## Creating an OpenAI API Key

### Step 1: Create an OpenAI Account
1. Visit [OpenAI's Platform](https://platform.openai.com)
2. Click "Sign Up" if you don't have an account
3. Complete the registration process

### Step 2: Set Up Billing
1. Log in to your OpenAI account
2. Navigate to "Billing" in the left sidebar
3. Click "Add Payment Method"
4. Enter your payment details
5. Set up a spending limit (recommended for testing)

### Step 3: Generate API Key
1. Go to [API Keys](https://platform.openai.com/api-keys) section
2. Click "Create new secret key"
3. Give your key a descriptive name (e.g., "Drupal AI Integration")
4. Copy the generated API key immediately
   - Note: You won't be able to see this key again after leaving the page

## Configure API Key on a Drupal Website

### Step 1: Install Required Modules
```bash
lando drush en key key_value_field -y
```

### Step 2: Configure Key Module
1. Go to `/admin/config/system/keys` in your Drupal site
2. Click "Add key"
3. Fill in the following details:
   - Key name: `openai_api_key`
   - Key type: `Authentication`
   - Key provider: `File`
   - Key value: Paste your OpenAI API key
4. Click "Save"

### Step 3: Configure AI Module Settings
1. Go to `/admin/config/ai/settings`
2. Select "OpenAI" as the AI provider
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
- Set up spending limits in your OpenAI account
- Monitor your API usage regularly

## Troubleshooting
If you encounter issues:
1. Verify the API key is correctly stored in the Key module
2. Check the Drupal logs for any API-related errors
3. Ensure your OpenAI account has sufficient credits
4. Verify your API key hasn't expired or been revoked
