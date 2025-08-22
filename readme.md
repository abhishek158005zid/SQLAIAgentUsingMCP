
This project implements a MCP Server that connects with Claude Desktop to execute SQL-based operations securely on Amazon Redshift. It uses a metadata file to control access to permitted tables and manages model context, prompts and resources for smooth communication.

# Installation & Setup Guide

## 1. Installation
Install **uv** 
```bash
pip install uv
```

## 2. Environment Setup
1. In the project root directory, create a `.env` file.  
2. Add the following environment variables :  
   ```env
   DB_USERNAME=
   DB_PASSWORD=

## 3. Run the Application
1. Navigate to the project directory.  
2. Run the application using:  
   ```bash
   uv run main.py

# File Details

1.**tools.py** → Contains MCP tools  
2. **resources.py** → Defines MCP resources  
3. **prompt.py** → Stores MCP prompt logic  
4. **settings.py** → Configuration file (e.g., database credentials)  
5. **main.py** → Entry point for running the MCP application  
6. **server.py** → Initializes and sets the global MCP object  
7. **helper.py** → Utility/helper functions  
8. **sql_permitted_tables.json** → Resource file specifying permitted SQL tables


## Connect MCP Server to Claude Desktop

To connect the MCP server with Claude Desktop:

**Step 1:** Open **Claude Desktop**
**Step 2:** Go to `Settings → Developer section → Edit config`
**Step 3:** Paste the following configuration into the `claude_desktop_config.json` file:

```json
{
  "mcpServers": {
    "sqlmcp": {
      "command": "npx",
      "args": [
        "mcp-remote",
        "http://localhost:8000/mcp"
      ]
    }
  }
}
``` 
