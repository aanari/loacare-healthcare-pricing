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

Use the live documentation for current connection and authentication guidance. The hosted server uses Streamable HTTP; clients should complete the server's advertised authorization flow when required.

## Available workflows

The server supports workflows for:

- Searching medical procedure billing codes.
- Finding U.S. healthcare providers and hospitals.
- Resolving source-labeled Loa entity profiles.
- Comparing published hospital price-transparency rows and available provider prices.
- Explaining price provenance and source labels.
- Submitting authenticated provider or hospital corrections for Loa review.

## Registry metadata

[`server.json`](./server.json) is the public metadata submitted to the official MCP Registry under `io.github.aanari/loacare-healthcare-pricing`.

This repository publishes integration metadata and documentation for Loa's hosted MCP server. The production application source is maintained separately.
