# DevContainer Configuration

This DevContainer provides a complete development environment for the Foundry Agents with OBO MCP Server project.

## Included Features

### Language & Runtime Support
- **Python 3.10**: For FastAPI backend (`foundry_agent_backend_api`), agent scripts (`foundry_agents`), and MCP server (`custom_jira_confluence_mcp_server`)
- **Node.js 18**: For React SPA (`spa_foundry_agent_webapp`)

### Azure Tools
- **Azure CLI**: For managing Azure resources and deployments
- **Azure Developer CLI (azd)**: For Azure-specific development workflows
- **Docker-in-Docker**: For building and running container images (needed for MCP server deployment)

## VS Code Extensions

The following extensions are pre-installed:
- Python language support and IntelliSense
- ESLint for JavaScript/TypeScript linting
- Prettier for code formatting
- Bicep for Azure infrastructure as code
- Azure Account integration

## Port Forwarding

The following ports are automatically forwarded:
- **3000**: React SPA frontend
- **8000**: Custom Atlassian MCP Server
- **8765**: FastAPI Backend API

## Getting Started

After opening the project in the DevContainer:

1. **Install Python dependencies** for each Python project:
   ```bash
   # Backend API
   cd foundry_agent_backend_api
   pip install -r requirements.txt
   
   # Agent Scripts
   cd ../foundry_agents
   pip install -r requirements.txt
   
   # MCP Server
   cd ../custom_jira_confluence_mcp_server
   pip install -r requirements.txt
   ```

2. **Install Node.js dependencies** for the React SPA:
   ```bash
   cd spa_foundry_agent_webapp
   npm install
   ```

3. **Configure environment files** by copying `.env.sample` to `.env` in each project directory and updating with your values.

4. Follow the main [README.md](../README.md) for detailed setup instructions.

> **Note**: The DevContainer provides an isolated environment, so you can install Python packages directly without creating additional virtual environments. However, if you prefer to use virtual environments (e.g., for local testing outside the container), you can create them as described in the main README.

## Troubleshooting

- If Python or Node.js commands are not found, try reloading the DevContainer window
- Ensure Docker is running if you need to build container images
- Azure CLI login: Run `az login` to authenticate with Azure
