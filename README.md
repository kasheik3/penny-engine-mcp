# Penny Engine — Agent Operations MCP server

**Registry namespace target:** `io.github.kasheik3/penny-engine`  
**GitHub repository:** https://github.com/kasheik3/penny-engine-mcp  
**Live remote MCP endpoint:** https://penny-agent-api-production.up.railway.app/mcp

This repository contains publishing metadata for the **already-running remote MCP server**. It does not contain Penny Engine's production backend code or any secrets.

## Features

- 16 free MCP tools, including `penny_choose_service` to match tasks to a supported paid API and `penny_fulfillment_preflight` to check catalog inputs before purchase.
- Structured-data processing, catalog checks, and deterministic commerce utilities.
- Separately hosted x402 paid API: https://penny-paid-batch-production.up.railway.app/openapi.json
- Paid requests advertise $0.001 USDC per request on Base. A buyer-controlled funded wallet must authorize payment; no third-party settlements have been independently verified yet.

## Connect an agent

Connect a remote **Streamable HTTP** MCP client to:

`https://penny-agent-api-production.up.railway.app/mcp`

Machine-readable descriptions: https://penny-agent-api-production.up.railway.app/tools

Buyer's quickstart: https://penny-agent-api-production.up.railway.app/agentcash-quickstart.md

## Publish to the official MCP Registry

1. Publish `README.md`, `server.json`, and `.github/workflows/publish-mcp.yml` to the **root** of the public GitHub repository `kasheik3/penny-engine-mcp`.
2. The workflow is configured to **run automatically** when `server.json` or the workflow is committed to `main`. Alternatively, open **Actions → Publish Penny Engine to MCP Registry → Run workflow**.
3. The workflow uses `mcp-publisher login github-oidc`; no personal access token or registry password needs to be added to this repository.
4. View the workflow logs, confirm a successful publication, and verify the entry at https://registry.modelcontextprotocol.io/ using `io.github.kasheik3/penny-engine`.

**Publishing status:** Repository files must be committed and the GitHub Actions publish job must succeed before treating the server as officially registered. Publishing does not prove customer payments or independent revenue.
