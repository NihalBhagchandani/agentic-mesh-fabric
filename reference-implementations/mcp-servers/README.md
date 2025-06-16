# MCP Servers Reference

This folder contains standard configuration files for running various MCP servers.
- Each config is located in `configs/` and follows the official [MCP server](https://github.com/modelcontextprotocol/servers) format.
- Refer to [awesome-mcp-servers](https://github.com/punkpeye/awesome-mcp-servers) for additional MCP server implementations.

## Usage

Select a config and run the corresponding command as specified. For Docker-based servers, you can use the provided `docker-compose.yml` for convenient orchestration.

## Examples

### Kubernetes MCP Server

To run the Kubernetes MCP server individually:

```bash
docker run -i --rm -v ~/.kube:/home/appuser/.kube:ro ghcr.io/alexei-led/k8s-mcp-server:latest
```

Alternatively, use Docker Compose:

```bash
docker compose up -d k8s-mcp-server
```

### Okta MCP Server

To run the Okta MCP server individually:

```bash
docker run -i --rm -e OKTA_CLIENT_ORGURL="https://your-org.okta.com" -e OKTA_API_TOKEN="your_api_token" fctrid/okta-mcp-server-stdio:latest
```

Alternatively, use Docker Compose:

```bash
docker compose up -d okta-mcp-server
```

Ensure you replace placeholder environment variables (`OKTA_CLIENT_ORGURL` and `OKTA_API_TOKEN`) with your actual Okta details.
