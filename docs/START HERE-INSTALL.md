## Requirements

### System Requirements
- Lando v3.23.26+
- PHP 8.1 or higher
- Composer 2.x
- MySQL 8.0 or MariaDB 10.4+
- Drush 11.x or higher
- Git

### AI Integration Requirements
Choose one of the following AI providers:

- OpenAI API key (for GPT integration)
  - Note: Requires setting up a payment method on OpenAI's platform
  - [Detailed OpenAI API Key Setup Guide](OPENAI-API-KEY-SETUP.md)

#### OR

- Google Gemini API key (for Gemini integration)
  - Note: Requires setting up billing on Google Cloud Platform
  - [Detailed Gemini API Key Setup Guide](GEMINI-API-KEY-SETUP.md)

## Installation

### Step 1: Clone the Repository
```bash
git clone [repository-url]
cd drupalAIApp
```

### Step 2: Install Dependencies
```bash
composer install
```

### Step 3: Start Lando
```bash
lando start
```
This command will:
- Build the Docker containers
- Set up the local environment
- Create the database
- Configure the web server

### Step 4: Install Drupal
```bash
lando drush site:install --db-url=mysql://drupal10:drupal10@database/drupal10 -y
```

### Step 5: Clear Cache
```bash
lando drush cr
```

### Step 6: Access Your Site
- Local URL: https://drupalaiapp.lndo.site
- Default login credentials:
  - Username: admin
  - Password: admin

### Troubleshooting
If you encounter any issues:
1. Check if all containers are running:
```bash
lando status
```

2. Rebuild the environment if needed:
```bash
lando rebuild -y
```

3. Check the logs:
```bash
lando logs
```

### 