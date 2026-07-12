# Walrus Finance Agent
A Persistent Onchain Trading & DeFi Intelligence Agent powered by Walrus Memory

## Project Overview
Walrus Finance Agent is a professional-grade AI trading assistant that combines real-time market intelligence with persistent memory on Walrus. It remembers user risk profiles, portfolio allocations, trading preferences, and past analyses — delivering consistent, personalized insights across sessions.

Designed specifically for the Walrus Memory Prompt Jam, this agent demonstrates practical, production-ready use of Walrus MemWal MCP.

## Key Features
* **Persistent long-term memory** via Walrus MemWal MCP
* **Real-time price data** from Coingecko MCP
* **Technical analysis** and risk management
* **Beautiful, professional response formatting**
* **Full ReAct reasoning** with transparent tool usage
* **Works directly** in Claude Desktop and Cursor

## Requirements
* Claude Desktop or Cursor with MCP support enabled
* Walrus MemWal MCP integration (using the official Walrus configuration)
* Coingecko MCP tool for real-time market data
* Internet connection

## Installation & Setup (Step-by-Step)

### Step 1: Configure MCP from Walrus Documentation
Instead of hosting your own server, integrate the agent directly using the official Walrus MCP configurations. Follow the setup instructions provided in the Walrus documentation to plug the MemWal MCP directly into your local environment using the public or managed endpoints.

### Step 2: Configure AI Environment
Copy the JSON configurations below and add them directly to your environment config file (`claude_desktop_config.json` for Claude Desktop, or via the UI settings under `MCP Servers` in Cursor).

#### For Claude Desktop (`claude_desktop_config.json`):
```json
{
  "mcpServers": {
    "walrus-memwal": {
      "command": "npx",
      "args": [
        "-y",
        "@mysten-incubation/memwal-mcp"
      ],
      "env": {
        "ENV": "prod",
        "NAMESPACE": "walrus-finance-agent"
      }
    },
    "coingecko": {
      "command": "npx",
      "args": [
        "mcp-remote",
        "https://mcp.api.coingecko.com/mcp"
      ]
    }
  }
}
```

*Note: For **Cursor**, add each server manually under `Settings` → `Tools & Integrations` → `MCP Servers` using `npx` as the command, and passing the respective values from the `args` and `env` blocks above.*

### Step 3: Load System Prompt
1. Copy the content from `PROMPT.md`
2. Paste it as System Prompt / Custom Instructions in your project
3. Start a new conversation

## Usage Guide
Tell the agent your trading profile (risk tolerance, portfolio size, preferences). Ask trading-related questions normally. The agent will automatically recall memories, fetch live data, analyze, and save new insights.

### Example Commands:
1. *"I am a conservative trader with $50k portfolio, mainly BTC and ETH"*
2. *"Perform full technical analysis on BTC right now"*
3. *"Suggest risk-managed trade setups for this week"*
4. *"Analyze my past portfolio performance and check if my risk tolerance has shifted"*
5. *"Compare current gas trends on Sui with live token prices from Coingecko"*
6. *"What are the key support and resistance levels for ETH today?"*
7. *"Review my trading preference history and update my strategy to aggressive growth"*
8. *"Generate a DeFi yield farming comparison based on my historical token preferences"*
9. *"Draft a risk mitigation plan assuming a 15% market drawdown tonight"*
10. *"Check my current asset allocation memory and cross-reference with live prices to spot deviations"*
