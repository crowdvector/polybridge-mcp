# PolyBridge Search MCP

Read-only prediction-market search for Claude Desktop and MCP clients.

## Scope

PolyBridge Search MCP exposes one tool only:

- `polybridge_search`

It is:

- Search-only
- Read-only

Search results return ranked prediction-market retrieval results. Scores are relevance/ranking
scores, not probabilities or forecasts.

## Non-goals

PolyBridge Search MCP does not provide:

- trading
- forecasts
- payments
- sessions
- market history
- market lookup
- Situation Room

## Installation

1. Download `polybridge-search-v0.1.0.mcpb` from the GitHub Release for this repository.
2. Open or import the file in Claude Desktop.
3. Enable the extension.

## Basic usage

Ask Claude:

> Use PolyBridge Search to find active prediction markets related to US recession risk.

## API key configuration

- Anonymous mode works with lower limits.
- Builder API keys raise the Claude Desktop MCP limit to `top_k_per_dimension <= 50`.
- Configure `POLYBRIDGE_API_KEY` in the Claude Desktop extension settings.
- Do not paste API keys into chat.

## Limits

Anonymous / local with no key:

- `top_k_per_dimension <= 20`
- `dimensions <= 4`

With `POLYBRIDGE_API_KEY`:

- `top_k_per_dimension <= 50`
- `dimensions <= 4`

## Supported dimensions

- `direct`
- `upstream`
- `downstream`
- `correlated`

## REST API

PolyBridge Search is also available through the public REST Search API:

- `https://oracle-api-rz5a43fxuq-ue.a.run.app/v1/search`

## Hosted MCP

Hosted MCP is currently beta / request access.

## Support

For Builder API keys or higher limits, contact the PolyBridge team.
