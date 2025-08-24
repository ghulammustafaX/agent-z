## Overview
Agent Z is a Python-based Twitter automation system that generates and posts AI-powered content using Claude API. The system can create tweets about AI tools, programming tips, and technology knowledge.

| Azure - 1 | Azure - 2 |
|---------|----------|
| <img width="928" height="349" alt="image" src="https://github.com/user-attachments/assets/dc1f992f-e851-4470-b595-56e75dcf7a46" /> | <img width="938" height="370" alt="image" src="https://github.com/user-attachments/assets/37b2a295-3e5b-4191-81b5-7419c0d9ffe5" /> |

| XAccount - 1 | XAccount - 2 |
|---------|----------|
| <img width="899" height="359" alt="image" src="https://github.com/user-attachments/assets/015aeb10-ff3c-4ae7-a55f-26f4c9965e28" /> | <img width="878" height="366" alt="image" src="https://github.com/user-attachments/assets/53dfdda6-c274-4af7-a2ae-262c6130febc" /> |

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
