# MCP Servers Reference

This folder contains standard configuration files for running various MCP servers.
- Each config is in `configs/` and follows the official [MCP server](https://github.com/modelcontextprotocol/servers) format.
- also refer [awesome-mcp-servers](https://github.com/punkpeye/awesome-mcp-servers) for more mcp-servers.

## Usage

Choose a config and run the command as specified. For Docker-based servers, you can use the provided `docker-compose.yml` for orchestration.

## Example

To run the Kubernetes MCP server:

`docker run -i --rm -v ~/.kube:/home/appuser/.kube:ro ghcr.io/alexei-led/k8s-mcp-server:latest`
