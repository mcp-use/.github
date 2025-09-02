<div align="center" style="margin: 0 auto; max-width: 80%;">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="static/logo_white.svg">
    <source media="(prefers-color-scheme: light)" srcset="static/logo_black.svg">
    <img alt="mcp use logo" src="static/logo_white.svg" width="80%" style="margin: 20px auto;">
  </picture>
</div>

<h1 align="center">mcp-use</h1>

<p align="center">
    <a href="https://pypi.org/project/mcp_use/" alt="PyPI Version">
        <img src="https://img.shields.io/pypi/v/mcp_use.svg"/></a>
    <a href="https://pypi.org/project/mcp_use/" alt="PyPI Downloads">
        <img src="https://static.pepy.tech/badge/mcp-use" /></a>
    <a href="https://docs.mcp-use.io" alt="Documentation">
        <img src="https://img.shields.io/badge/docs-mcp--use.io-blue" /></a>
    <a href="https://mcp-use.io" alt="Website">
        <img src="https://img.shields.io/badge/website-mcp--use.io-blue" /></a>
    <a href="https://github.com/pietrozullo/mcp-use/blob/main/LICENSE" alt="License">
        <img src="https://img.shields.io/github/license/pietrozullo/mcp-use" /></a>
    <a href="https://github.com/pietrozullo/mcp-use/stargazers" alt="GitHub stars">
        <img src="https://img.shields.io/github/stars/pietrozullo/mcp-use?style=social" /></a>
</p>
<p align="center">
    <a href="https://x.com/pietrozullo" alt="Twitter Follow - Pietro">
        <img src="https://img.shields.io/twitter/follow/Pietro?style=social" /></a>
    <a href="https://x.com/pederzh" alt="Twitter Follow - Luigi">
        <img src="https://img.shields.io/twitter/follow/Luigi?style=social" /></a>
    <a href="https://discord.gg/XkNkSkMz3V" alt="Discord">
        <img src="https://dcbadge.limes.pink/api/server/XkNkSkMz3V?style=flat" /></a>
</p>

🌐 MCP-Use is the open source way to connect **any LLM to any MCP server** and build custom agents that have tool access, without using closed source or application clients.

- If you want to get started quickly, check out [mcp-use.com website](https://mcp-use.com/) to build and deploy agents with your favorite MCP servers.
- Visit the [mcp-use docs](https://docs.mcp-use.com/) to get started with mcp-use library.
- Python SDK: [mcp-use](https://github.com/mcp-use/mcp-use)
- TypeScript SDK: [mcp-use-ts](https://github.com/mcp-use/mcp-use-ts)

## 🧐 What is mcp-use?

`mcp-use` is an open source library that enables developers to connect any LLM to any MCP server, allowing the creation of custom agents with tool access without relying on closed-source or application-specific clients.

## ✨ Just like this

Here's a quick example of how you can use `mcp-use`:

```python
import asyncio
from langchain_openai import ChatOpenAI
from mcp-use import MCPAgent, MCPClient

async def main():
    client = MCPClient(config= {"mcpServers":{
    "playwright": {
        "command": "npx",
        "args": ["@playwright/mcp@latest"],
        "env": {"DISPLAY": ":1"}
    }}})
    # Create LLM
    llm = ChatOpenAI(model="gpt-4o", api_key=...)
    # Create agent with tools
    agent = MCPAgent(llm=llm, client=client, max_steps=30)
    # Run the query
    result = await agent.run("Find the best restaurant in San Francisco")

if __name__ == "__main__":
    asyncio.run(main())
```

➡️ **[Create your own with our Builder](https://mcp-use.io/builder)**

## 🚀 Key Features

*   **💻 Open Source**: Connect any LLM to any MCP server without vendor lock-in.
*   **⚙️ Flexible Configuration**: Support for any MCP server through a simple configuration system.
*   **⚙️ Easy Setup**: Simple JSON-based configuration for MCP server integration.
*   **🤖 Universal LLM Support**: Compatible with any LangChain-supported LLM provider.
*   **🔌 HTTP Connection**: Connect to MCP servers running on specific HTTP ports for web-based integrations.
*   **🔀 Dynamic Server Selection**: Agents can dynamically choose the most appropriate MCP server for the task.

## 🏁 Getting Started

*   **📥 Installation**: [Install mcp-use and set up your environment](https://docs.mcp-use.io/quickstart)
*   **📖 Configuration**: [Learn how to configure mcp-use with your MCP server](https://docs.mcp-use.io/essentials/configuration)

<div align="center" style="margin-top: 30px;">
  <a href="https://mcp-use.io/tutorial" style="text-decoration: none;"> <!-- Adjust link as needed -->
    <button style="background-color: #007bff; color: white; padding: 10px 20px; border: none; border-radius: 5px; cursor: pointer; font-size: 16px; margin-right: 10px;">
      View Tutorials
    </button>
  </a>
  <a href="https://mcp-use.io/what-should-we-build-next" style="text-decoration: none;"> <!-- Adjust link as needed -->
    <button style="background-color: transparent; color: #007bff; padding: 10px 20px; border: 1px solid #007bff; border-radius: 5px; cursor: pointer; font-size: 16px;">
      Suggest a Feature
    </button>
  </a>
</div>

---

*We are constantly working to improve `mcp-use`. Check out what we're planning and suggest new features!* 
