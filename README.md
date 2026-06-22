# PolyBridge MCP

PolyBridge MCP provides read-only Search and Forecast tools. Hosted MCP is available
at `https://mcp.polybridge.ai/mcp`. No API key is required at anonymous limits.
This repository also publishes the local Claude Desktop MCPB package.

## Tools

PolyBridge MCP exposes two read-only tools:

- `polybridge_search`
- `polybridge_forecast`

Both tools are read-only. They do not place trades, submit orders, handle custody,
or perform write actions.

### Search

`polybridge_search` retrieves relevant prediction markets for a topic or question.

- Search results return ranked prediction-market retrieval results.
- Scores are relevance/ranking scores, not probabilities.
- Local MCPB Search works without `POLYBRIDGE_API_KEY` at anonymous limits.
- Configure `POLYBRIDGE_API_KEY` only for higher usage.
- If `dimensions` is omitted, Search uses all supported dimensions by default:
  `direct`, `upstream`, `downstream`, and `correlated`.

### Forecast

`polybridge_forecast` generates read-only forecasts using PolyBridge market search and evidence synthesis.

- Forecast responses return forecast outputs and probabilities.
- Local MCPB Forecast works without `POLYBRIDGE_API_KEY` at anonymous limits.
- Configure `POLYBRIDGE_API_KEY` only for higher usage.
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
- custody
- write actions

## Installation

1. Download `polybridge-mcp-v0.2.5.mcpb` from the `polybridge-mcp-v0.2.5` GitHub Release for this repository.
   Release: `https://github.com/crowdvector/polybridge-mcp/releases/tag/polybridge-mcp-v0.2.5`
2. Open or import the file in Claude Desktop.
3. Enable the extension.
4. No API key is required at anonymous limits for Search and Forecast. Configure `POLYBRIDGE_API_KEY` only for higher usage.

## Basic Usage

Ask Claude:

> Use PolyBridge Search to find active prediction markets related to US recession risk.

Or:

> Use PolyBridge Forecast to estimate the probability of a US recession in 2026.

## API Key Configuration

- Local MCPB Search and Forecast work without `POLYBRIDGE_API_KEY` at anonymous limits.
- Configure `POLYBRIDGE_API_KEY` in the Claude Desktop extension settings only for higher usage.
- Invalid configured auth fails hard and does not fall back to anonymous.
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

The public REST API supports Search and Forecast without an API key at anonymous limits.
Add an API key for higher usage.

- Search: `https://api.polybridge.ai/v1/search`
- Forecast: `https://api.polybridge.ai/v1/forecast`

## Hosted MCP

Hosted MCP is available at `https://mcp.polybridge.ai/mcp`. No API key is
required at anonymous limits. Add an API key or supported OAuth for higher
usage. Invalid configured auth fails hard and does not fall back to anonymous.

## Support

For higher usage or access questions, contact the PolyBridge team.
