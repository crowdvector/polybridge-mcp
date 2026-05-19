# Changelog

## PolyBridge MCP v0.2.0

- Adds the read-only `polybridge_forecast` tool.
- Keeps the read-only `polybridge_search` tool.
- Updates the public package name and copy to `PolyBridge MCP`.
- Updates the default API base URL to `https://api.polybridge.ai`.
- Forecast requires `forecast:read`.
- A `search_forecast` key can power both Search and Forecast.
- The package remains read-only and does not support trading or order placement.

## PolyBridge Search MCP v0.1.0

Initial public beta release.

- Adds Claude Desktop MCP extension for PolyBridge Search.
- Exposes one read-only tool: `polybridge_search`.
- Supports anonymous Search usage with bounded limits.
- Supports optional `POLYBRIDGE_API_KEY` configuration for higher Builder limits.
- Returns ranked prediction-market search results.
- Scores are relevance/ranking scores, not probabilities or forecasts.
- This was the initial Search-only public release.

Explicitly out of scope:

- No trading.
- No forecast generation.
- No payments.
- No sessions.
- No market history.
- No market lookup.
- No Situation Room.
- Hosted MCP remains beta / request access.
