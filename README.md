## Overview

Agent Z is a Python-based Twitter automation system that generates and posts AI-powered content using Claude API. The system can create tweets about AI tools, programming tips, and technology knowledge.

## Architecture

### Core Components

1. **Content Generator** 
   - Generates AI-powered content using Claude API
   - Falls back to predefined content if API is unavailable
   - Supports multiple content types

2. **Twitter Client** 
   - Handles Twitter API interactions
   - Manages rate limiting and error handling
   - Posts tweets and manages content

3. **Scheduler** 
   - Manages posting schedule
   - Handles continuous and single execution modes
   - Integrates with content generator and Twitter client

4. **Configuration** 
   - Manages environment variables and settings
   - Validates API keys and configuration
   - Provides centralized configuration management

### Data Models

- **Tweet**: Represents a tweet with content and metadata
- **Topic**: Represents content topics and categories
- **ContentType**: Enum for different types of content

## Configuration

### Environment Variables

Create a `.env` file with the following variables:

```env
# Twitter API
TWITTER_API_KEY=your_api_key
TWITTER_API_SECRET=your_api_secret
TWITTER_ACCESS_TOKEN=your_access_token
TWITTER_ACCESS_TOKEN_SECRET=your_access_token_secret

# Claude API
CLAUDE_API_KEY=your_claude_api_key

# Application Settings
POSTING_INTERVAL_MINUTES=60
MAX_POSTS_PER_DAY=24
TEST_MODE=false
```

## Usage

### Running the Application

1. **Install dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

2. **Configure environment**:
   - Copy `.env.example` to `.env`
   - Add your API keys

3. **Run the application**:
   ```bash
   python src/main.py
   ```

### Command Line Options

- `--mode`: Choose between 'test' and 'production'
- `--run-once`: Run once and exit
- `--content-type`: Specify content type (ai_tools, programming_tips, tech_knowledge, random)

## Azure Functions Deployment

The project includes Azure Functions deployment capabilities:

1. **Deploy to Azure**:
   ```bash
   # Using PowerShell
   .\scripts\deploy-to-azure.ps1
   
   # Using Bash
   ./scripts/deploy-to-azure.sh
   
   # Using Python
   python scripts/deploy_azure.py
   ```

2. **Check deployment status**:
   ```bash
   python scripts/check_deployment_status.py
   ```

## Testing

Run tests using pytest:

```bash
# Run all tests
pytest tests/

# Run specific test categories
pytest tests/test_*.py
pytest tests/manual_*.py
```

## Development

### Project Structure

```
agent_z/
├── src/                   # Core application
├── azure/                 # Azure Functions deployment
├── tests/                 # Test suite
├── scripts/               # Utility scripts
├── data/                  # Configuration data
├── logs/                  # Application logs
└── docs/                  # Documentation
```

### Adding New Features

1. Create feature branch
2. Implement changes in appropriate modules
3. Add tests in `tests/` directory
4. Update documentation
5. Submit pull request

## Troubleshooting

### Common Issues

1. **API Rate Limits**: The system handles rate limiting automatically
2. **Configuration Errors**: Check `.env` file and API key validity
3. **Content Generation Failures**: System falls back to predefined content

### Logs

Check `logs/twitter_automation.log` for detailed application logs.

## License

MIT License - see LICENSE file for details.
