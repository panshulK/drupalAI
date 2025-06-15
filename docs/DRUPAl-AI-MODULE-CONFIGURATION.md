# Drupal AI Module Configuration Guide

## Prerequisites
Before configuring the AI module, ensure you have:
1. A working Drupal installation
2. An API key from either OpenAI or Google Gemini
3. The Key module installed for secure API key storage

## Step 1: Install Required Modules
```bash
# Install the Key module and its dependencies
lando drush en key -y

# Install the AI module
lando drush en ai -y
```

## Step 2: Install AI Providers
Install your preferred AI provider(s) using Composer:

For OpenAI:
```bash
composer require 'drupal/ai_provider_openai:^1.1'
```

For Google Gemini:
```bash
composer require 'drupal/gemini_provider:^1.0@beta'
```

After installing the providers, enable them:
```bash
# For OpenAI
lando drush en ai_provider_openai -y

# For Gemini
lando drush en gemini_provider -y
```

## Step 3: Configure API Key Storage
Before proceeding, make sure you have your API key ready. For detailed instructions on obtaining and setting up your API key, refer to:
- [OpenAI API Key Setup Guide](OPENAI-API-KEY-SETUP.md)
- [Gemini API Key Setup Guide](GEMINI-API-KEY-SETUP.md)

Once you have your API key, configure it in Drupal:

1. Go to `/admin/config/system/keys` in your Drupal site
2. Click "Add key"
3. Configure based on your chosen AI provider:

   For OpenAI:
   - Key name: `openai_api_key`
   - Key type: `Authentication`
   - Key provider: `File`
   - Key value: Your OpenAI API key

   OR

   For Gemini:
   - Key name: `gemini_api_key`
   - Key type: `Authentication`
   - Key provider: `File`
   - Key value: Your Gemini API key

4. Click "Save"

## Step 4: Configure AI Module Settings
1. Navigate to `/admin/config/ai/settings`
2. Select your preferred AI provider:
   - OpenAI
   - Google Gemini
3. In the API Key field, select the key you created in Step 3
4. Configure additional settings:
   - Model selection (e.g., GPT-4, GPT-3.5-turbo for OpenAI)
   - Temperature setting (0.0 to 1.0)
   - Maximum tokens per request
   - Response timeout
5. Click "Save configuration"

## Step 5: Enable AI Features
1. Go to `/admin/config/ai/features`
2. Enable desired features:
   - Content Generation
   - Content Analysis
   - Smart Search
   - Automated Tagging
   - Other available features

## Step 6: Test the Configuration
1. Clear the cache:
```bash
lando drush cr
```

2. Test a basic AI operation:
   - Go to any content creation page
   - Look for the AI assistance button
   - Try generating content or getting suggestions

## Common Configuration Options

### Content Generation Settings
- Maximum content length
- Tone and style preferences
- Language settings
- Content type restrictions

### Analysis Settings
- Sentiment analysis depth
- Keyword extraction options
- Content categorization rules
- Custom analysis parameters

### Search Settings
- AI-enhanced search relevance
- Search result customization
- Query understanding options
- Result ranking preferences

## Troubleshooting

### Common Issues
1. API Key Not Working
   - Verify the key is correctly stored
   - Check if the key has expired
   - Ensure proper permissions

2. Module Not Responding
   - Clear the cache
   - Check the logs at `/admin/reports/dblog`
   - Verify API quota limits

3. Performance Issues
   - Adjust timeout settings
   - Check server resources
   - Optimize request frequency

### Getting Help
- Check the module's issue queue
- Review the documentation
- Contact support if needed

## Best Practices
1. Start with conservative settings
2. Monitor API usage regularly
3. Set appropriate rate limits
4. Keep your API keys secure
5. Regularly update the module
6. Test features in a staging environment first
