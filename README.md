# PolyBridge MCP

PolyBridge MCP provides read-only Search and Forecast tools. Hosted MCP is available
at `https://mcp.polybridge.ai/mcp` and works without a key at anonymous limits.
This repository also publishes the local Claude Desktop MCPB package.

## Tools

PolyBridge MCP exposes two read-only tools:

- `polybridge_search`
- `polybridge_forecast`

Both tools are read-only. They do not place trades, submit orders, or perform write actions.

### Search

`polybridge_search` retrieves relevant prediction markets for a topic or question.

- Search results return ranked prediction-market retrieval results.
- Scores are relevance/ranking scores, not probabilities.
- Local MCPB Search can work without `POLYBRIDGE_API_KEY` at lower limits.
- If `dimensions` is omitted, Search uses all supported dimensions by default:
  `direct`, `upstream`, `downstream`, and `correlated`.

### Forecast

`polybridge_forecast` generates read-only forecasts using PolyBridge market search and evidence synthesis.

- Forecast responses return forecast outputs and probabilities.
- Local MCPB Forecast still requires `POLYBRIDGE_API_KEY` with `forecast:read`.
- Hosted MCP and the public REST Forecast endpoint are separate and support no-key
  Forecast at anonymous limits.
- A `search_forecast` key can power both Search and Forecast.

## Non-goals

PolyBridge MCP does not provide:

- trading
- orders
- payments
- sessions
- market history
- market lookup
- Situation Rooms
- internal APIs

## Installation

1. Download `polybridge-mcp-v0.2.4.mcpb` from the `polybridge-mcp-v0.2.4` GitHub Release for this repository.
   Release: `https://github.com/crowdvector/polybridge-search-mcp/releases/tag/polybridge-mcp-v0.2.4`
2. Open or import the file in Claude Desktop.
3. Enable the extension.
4. For the local MCPB package, configure `POLYBRIDGE_API_KEY` if you want Forecast or higher Search limits.

## Basic Usage

Ask Claude:

> Use PolyBridge Search to find active prediction markets related to US recession risk.

Or:

> Use PolyBridge Forecast to estimate the probability of a US recession in 2026.

## API Key Configuration

- Local MCPB Search can work without `POLYBRIDGE_API_KEY` at lower limits.
- For the local MCPB package, configure `POLYBRIDGE_API_KEY` in the Claude Desktop extension settings if you want Forecast or higher Search limits.
- Use the PolyBridge Developer Console to create a Search+Forecast key.
- A `search_forecast` key can power both tools.
- Do not paste API keys into chat.

## Search Limits

Anonymous / local with no key:

- `top_k_per_dimension <= 20`
- `dimensions <= 4`

With `POLYBRIDGE_API_KEY`:

- `top_k_per_dimension <= 50`
- `dimensions <= 4`

## Supported Search Dimensions

- `direct`
- `upstream`
- `downstream`
- `correlated`

## REST API

The public REST API supports no-key Search and Forecast at anonymous limits.
Add an API key for higher usage.

- Search: `https://api.polybridge.ai/v1/search`
- Forecast: `https://api.polybridge.ai/v1/forecast`

## Hosted MCP

Hosted MCP is available at `https://mcp.polybridge.ai/mcp`. It supports no-key
Search and Forecast at anonymous limits. Add an API key or use supported OAuth
for higher usage.

## Support

For API keys, Forecast access, or higher limits, contact the PolyBridge team.
