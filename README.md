# Box Agent for Google ADK

This project implements a custom agent for the Google Agent Development Kit (ADK) that allows users to interact with Box content using natural language queries.

## Overview

The Box Agent leverages the Box AI Agents Toolkit to provide a seamless interface for searching, accessing, and analyzing content stored in Box. Users can ask questions about documents, search for files, and extract data using natural language.

## Features

- **Authentication and Identity**: Check who you are in Box and verify connectivity
- **File and Folder Search**: Find files and folders by name, content, or other criteria
- **Content Reading**: Extract and read text from Box files
- **Folder Navigation**: List folder contents and navigate the Box file structure
- **AI-Powered Analysis**: Ask questions about documents using Box AI
- **Data Extraction**: Extract structured data from documents using Box AI

## Prerequisites

- Python 3.13+
- Google ADK 0.5.0+
- Box AI Agents Toolkit 0.0.42+
- Box Developer credentials (CCG application)

## Installation

1. Clone the repository

```bash
git clone https://github.com/box-community/google-adk-box-agent.git
cd google-adk-box-agent
```

2. [Install uv](https://docs.astral.sh/uv/getting-started/installation/) (if not already installed)



3. Create a virtual environment and install dependencies

```bash
uv sync
uv lock
```

The project uses a uv.lock file to ensure deterministic installations across environments.

## Configuration

Create a `.env` file in the root directory with the following configuration:

```
# Google AI configuration
GOOGLE_GENAI_USE_VERTEXAI=FALSE
GOOGLE_API_KEY=your_google_api_key

# Box API configuration
BOX_CLIENT_ID=your_box_client_id
BOX_CLIENT_SECRET=your_box_client_secret
BOX_SUBJECT_TYPE=user
BOX_SUBJECT_ID=your_box_user_id
```

Replace the placeholder values with your actual credentials:
- `GOOGLE_API_KEY`: Your Google API key for Google Generative AI
- `BOX_CLIENT_ID`: Your Box application client ID
- `BOX_CLIENT_SECRET`: Your Box application client secret
- `BOX_SUBJECT_ID`: Your Box user ID

Note: Keep your `.env` file secure and never commit it to version control.

## Usage

### Starting the Agent

Run the agent using the ADK CLI:

```bash
uv run adk web
```

### Example Queries

- "Who am I in Box?"
- "Search for files containing 'quarterly report'"
- "Find folders named 'Projects'"
- "Read file 123456789"
- "What's in the Marketing folder?"
- "Ask Box AI about file 123456789: What is the main conclusion of this document?"
- "Extract invoice data from file 123456789"

## Project Structure

- `box_agent/`: Main package directory
  - `__init__.py`: Package initialization
  - `agent.py`: Root agent implementation
  - `sub_agents/`: Contains specialized sub-agents
    - `box_agent.py`: Core Box functionality agent
  - `tools/`: Tool implementations
    - `box_agent_tools.py`: Box-specific tool wrappers

## Acknowledgements

- [Box AI Agents Toolkit](https://github.com/box-community/box-ai-agents-toolkit)  
- [Google Agent Development Kit (ADK)](https://google.github.io/adk-docs/)
