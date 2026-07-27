# Loa Healthcare Pricing MCP Server

Loa's hosted Model Context Protocol server gives MCP-capable assistants access to source-labeled healthcare pricing, CPT and HCPCS code search, U.S. provider and hospital discovery, and Loa entity profiles.

- [Live MCP documentation](https://www.loacare.com/mcp)
- [Official MCP Registry listing](https://registry.modelcontextprotocol.io/?q=io.github.aanari%2Floacare-healthcare-pricing)
- [Healthcare pricing API](https://www.loacare.com/api-partnership)
- [Data sources and methodology](https://www.loacare.com/methodology)

## Remote endpoint

```text
https://www.loacare.com/api/mcp
```

The hosted server uses Streamable HTTP. Clients should complete the server's advertised OAuth flow when a tool call requires authentication.

### Native remote configuration

Use this configuration with clients that support remote MCP server URLs:

```json
{
  "mcpServers": {
    "loacare": {
      "url": "https://www.loacare.com/api/mcp"
    }
  }
}
```

For clients that require a local command, use the `mcp-remote` bridge:

```json
{
  "mcpServers": {
    "loacare": {
      "command": "npx",
      "args": [
        "-y",
        "mcp-remote",
        "https://www.loacare.com/api/mcp"
      ]
    }
  }
}
```

See the [live MCP documentation](https://www.loacare.com/mcp) for current authentication, rate-limit, and troubleshooting guidance.

## Available workflows

The server supports workflows for:

- Searching medical procedure billing codes.
- Finding U.S. healthcare providers and hospitals.
- Resolving source-labeled Loa entity profiles.
- Comparing published hospital price-transparency rows and available provider prices.
- Explaining price provenance and source labels.
- Submitting authenticated provider or hospital corrections for Loa review.

## Available tools

The production server currently advertises 12 tools:

- `search_cpt_codes`
- `suggest_procedures`
- `search_providers`
- `search_hospitals`
- `search_entities`
- `get_entity_profile`
- `get_entity_prices`
- `get_hospital_pricing`
- `get_market_pricing`
- `get_pricing_estimate`
- `explain_price_sources`
- `submit_entity_update_request`

The public discovery methods `initialize`, `notifications/initialized`, `ping`, and `tools/list` can be used without authentication. Tool execution remains OAuth-protected.

## Data scope

Loa returns public healthcare pricing and directory data. It does not require or return Protected Health Information. Pricing responses identify their source labels so clients can distinguish hospital machine-readable-file rows, provider-published prices, market estimates, and reviewed corrections.

## Registry metadata

[`server.json`](./server.json) is the public metadata submitted to the official MCP Registry under `io.github.aanari/loacare-healthcare-pricing`.

This repository publishes integration metadata and documentation for Loa's hosted MCP server. The production application source is maintained separately.
