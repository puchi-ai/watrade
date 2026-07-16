# WalFA - Walrus Finance Agent
A Persistent Onchain Trading & DeFi Intelligence Agent powered by Walrus Memory

## Project Overview
Walrus Finance Agent is a professional-grade AI trading assistant that combines real-time market intelligence with persistent memory on Walrus. It remembers user risk profiles, portfolio allocations, trading preferences, and past analyses — delivering consistent, personalized insights across sessions.

Designed specifically for the Walrus Memory Prompt Jam, this agent demonstrates practical, production-ready use of Walrus MemWal MCP.

## Key Challenges & Solutions (Why Walrus Finance Agent?)
Current AI trading assistants suffer from short-term amnesia, unreliable data sources, and rigid user experiences. Walrus Finance Agent addresses these critical pain points through a production-grade architecture:

*   **Persistent Context Across Sessions & Models:** Standard LLM interactions forget everything once a chat session ends or when you switch models/platforms. By utilizing Walrus MemWal MCP, this agent maintains a permanent, sovereign memory layer. Your risk profile, past portfolio adjustments, and trading preferences persist seamlessly across separate conversations, different AI platforms, or model upgrades.
*   **Guaranteed Real-Time, Non-Manipulated Data:** Making high-stakes trading decisions based on static or outdated data is a recipe for liquidation.
*   **Highly Flexible, AI-Driven Tailored Analysis:** Rigid algorithmic platforms lock users into fixed metrics. Leveraging advanced AI reasoning, this agent adapts dynamically to complex natural language requests, performing bespoke technical (RSI, MACD, EMA) and risk analysis on-demand based on your unique criteria.
*   **Intuitive & High-Clarity Visual Presentation:** Raw financial metrics can be overwhelming and difficult to skim. The agent explicitly formats heavy data into beautifully structured inline Markdown tables, clear procedural lists, and contextual highlights inside your chat canvas, utilizing sharp color-coding (🟩 for Bullish, 🟥 for Bearish) to turn dense metrics into actionable visual intelligence instantly.

## Key Features
* **Persistent long-term memory** via Walrus MemWal MCP
* **Deep Onchain Analytics** via custom Antigravity V2 integration
* **Advanced Technical Indicators** (Minimum 3: RSI, MACD, EMA Cross) calculated on-demand
* **High-Contrast Interface Color Psychology** (🟩 Bullish / 🟥 Bearish indicators with precise trend arrows)
* **Full ReAct reasoning** with transparent tool usage
* **Works directly** in Claude Desktop and Cursor

## Requirements
* Claude Desktop or Cursor with MCP support enabled
* Walrus MemWal MCP account and integration tokens
* Internet connection
* NodeJS

## Installation & Setup (Step-by-Step)

### Step 1: Register on Walrus Memory
Before setting up the agent, you must obtain your access credentials from the official protocol platform.
1. Navigate to the official [Walrus Memory](https://docs.walrus.site) registration portal.
2. Sign up, create your developer account, and provision your dedicated memory namespace keys.

### Step 2: Configure AI Environment & External Services
To deploy the required MCP endpoints, select from the integration options below based on your development workflow:

#### Option A: Claude Desktop Config (`claude_desktop_config.json`)
Open your system's global Claude configuration file and inject the following standard marketplace server endpoints:

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
    }
  }
}
```

#### Option B: Cursor IDE Configuration
1. Open Cursor and navigate to `Settings` → `Tools & Integrations` → `MCP Servers`.
2. Click **+ Add New MCP Server**.
3. Copy & paste in the JSON config above.

#### Option C: Antigravity V2 Manual Integration (.config Folder Setup)
Because Antigravity V2 is a standalone custom solution not available on public package marketplaces, you must package it manually inside your workspace root:
1. In your project's root directory, create a new folder named `.config`.
2. Inside the `.config` folder, create a configuration file named `mcp_config.json`.
3. Copy & paste in the JSON config above.

### Step 3: Load System Prompt
1. Copy the content from [PROMPT.md](https://github.com/puchi-ai/walfa/blob/main/PROMPT.md)
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
