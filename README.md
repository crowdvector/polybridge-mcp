# PolyBridge MCP

Read-only prediction-market Search and Forecast for Claude Desktop and MCP clients.

## Tools

PolyBridge MCP exposes two read-only tools:

- `polybridge_search`
- `polybridge_forecast`

Both tools are read-only. They do not place trades, submit orders, or perform write actions.

### Search

`polybridge_search` retrieves relevant prediction markets for a topic or question.

- Search results return ranked prediction-market retrieval results.
- Scores are relevance/ranking scores, not probabilities.
- Search can work anonymously with lower limits.

### Forecast

`polybridge_forecast` generates read-only forecasts using PolyBridge market search and evidence synthesis.

- Forecast responses return forecast outputs and probabilities.
- Forecast requires `POLYBRIDGE_API_KEY` with `forecast:read`.
- A `search_forecast` key can power both Search and Forecast.

## Non-goals

PolyBridge MCP does not provide:

- trading
- order placement
- payments
- sessions
- market history
- market lookup
- Situation Room

## Installation

1. Download `polybridge-mcp-v0.2.3.mcpb` from the `polybridge-mcp-v0.2.3` GitHub Release for this repository.
   Release: `https://github.com/crowdvector/polybridge-search-mcp/releases/tag/polybridge-mcp-v0.2.3`
2. Open or import the file in Claude Desktop.
3. Enable the extension.
4. Configure `POLYBRIDGE_API_KEY` in Claude Desktop if you want Forecast or higher Search limits.

## Basic Usage

Ask Claude:

> Use PolyBridge Search to find active prediction markets related to US recession risk.

Or:

> Use PolyBridge Forecast to estimate the probability of a US recession in 2026.

## API Key Configuration

- Search can work anonymously with lower limits.
- Configure `POLYBRIDGE_API_KEY` in the Claude Desktop extension settings if you want Forecast or higher Search limits.
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

PolyBridge MCP tools are also available through the public REST API:

- Search: `https://api.polybridge.ai/v1/search`
- Forecast: `https://api.polybridge.ai/v1/forecast`

## Hosted MCP

Hosted MCP is available at `https://mcp.polybridge.ai/mcp`.

- Hosted MCP supports `search:read`.
- Hosted MCP supports `forecast:read`.

## Support

For API keys, Forecast access, or higher limits, contact the PolyBridge team.
