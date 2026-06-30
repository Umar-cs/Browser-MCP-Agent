

https://github.com/user-attachments/assets/48507435-f596-459f-acfd-774455004020




# Browser MCP Agent

A Streamlit app that lets you control a real browser with natural-language commands using MCP, Playwright, and an LLM.

Instead of scripting browser automation manually, you can type requests like:

- "Go to https://github.com/lastmile-ai/mcp-agent"
- "Scroll down and summarize the page"
- "Click on a link and report what changed"

The app uses the `mcp-agent` framework to connect an LLM to Playwright tools, making it possible to navigate websites, interact with page elements, and summarize web content from a simple chat-style interface.

## Why this project?

Browser automation is powerful, but it often requires code, selectors, and step-by-step scripting. This project makes web interaction more accessible by turning browser actions into plain-English instructions that an agent can execute and explain.

## Features

- Natural-language browser commands
- Real browser control through Playwright
- Multi-step web navigation workflows
- Page interaction support including click, scroll, and type
- Web content extraction and summarization
- Streamlit interface for easy local use
- MCP-Agent configuration for OpenRouter or other OpenAI-compatible providers

## Tech Stack

- Python
- Streamlit
- MCP-Agent
- Playwright
- OpenRouter
- AsyncIO

## How It Works

1. The app initializes an `mcp-agent` application context.
2. A browser agent is created with access to the Playwright MCP server.
3. The LLM interprets the user command and chooses browser actions.
4. Playwright executes those actions in a real browser session.
5. The app returns the result as a readable natural-language response.

## Installation

### Prerequisites

- Python 3.10+
- Node.js and `npx`
- A valid API key in `mcp_agent.secrets.yaml`
- Access to an OpenAI-compatible endpoint such as OpenRouter

### Setup

```bash
pip install -r requirements.txt
streamlit run app.py
```

The Playwright MCP server is started from the app configuration using:

```yaml
command: "npx"
args: ["@playwright/mcp@latest"]
```

## Configuration

This project uses:

- `mcp_agent.config.yaml` for runtime, model, and MCP server settings
- `mcp_agent.secrets.yaml` for API keys and other sensitive values

## Example Use Cases

- Navigate to a site and summarize its contents
- Perform multi-step browsing tasks
- Extract information from documentation pages
- Prototype agent-based web automation workflows
- Explore how LLMs can control browser tools through MCP


## Future Improvements

- Add a visible browser session preview in the UI
- Save command history
- Add task templates for common browsing flows
- Improve error messages for missing credentials and tool startup
- Support screenshots and structured outputs in the interface
