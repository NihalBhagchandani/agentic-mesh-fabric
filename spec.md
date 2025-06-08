# Agentic Mesh Fabric — Architecture Specification

---

**Version:** 1.0  
**Author:** [Nihal Bhagchandani](https://github.com/NihalBhagchandani)  
**First published:** 08 June 2025  
**License:** Apache 2.0  

---

# Overview

**Agentic Mesh Fabric** is an open architecture pattern for building **safe, scalable, explainable, and composable enterprise AI** — combining:

✅ **Data Mesh** → domain-owned data and agents  
✅ **Data Fabric** → semantic discovery, lineage, and policy enforcement  
✅ **Agentic AI** → autonomous, tool-using agents powered by **Model Context Protocol (MCP)**  

In this architecture:

- **Domains own both their data products AND agents**  
- Agents interact with data via **MCP servers**  
- A **Fabric layer** provides **semantic abstraction**, **catalog/discovery**, **lineage**, and **policy enforcement**  

---

# Core Principles

## 🌐 Mesh Principles (Data Mesh):

- **Domain ownership of:**
  - Data products
  - AI agents
  - MCP servers  

- **Decentralization:**
  - No central bottlenecks
  - Domains innovate independently  

- **Product thinking:**
  - Data and agents treated as first-class products  
  - Discoverable, versioned, with SLAs  

---

## 🧵 Fabric Principles (Data Fabric):

- **Global metadata & catalog:** Agents can discover data & other agents semantically  
- **Semantic reasoning:** Agents reason on concepts, not raw tables
- **Lineage:** Full agent-to-data lineage → required for compliance
- **Data virtualization:** Agents can query logical APIs exposed by fabric
- **Policy-as-code:** Unified governance enforced centrally

---
## 🤖 Agentic Principles:

- **LLM-based agents:** Local LLMs (Ollama) → private and secure  
- **Planning & reasoning:** LangGraph / CrewAI → multi-step workflows  
- **MCP integration:** Agents dynamically pull context from MCP servers  
- **Tool-using AI:** SQL, APIs, files, code execution → composable intelligence  
- **Cross-domain collaboration:** Agents can discover & call other agents → Mesh of intelligence  

---

# Architecture Diagram

(See `/diagrams/architecture-mermaid.md` for Mermaid diagram)  
(See `/diagrams/agent-lifecycle.png` for agent lifecycle diagram)

---

# Reference Stack

| Layer | Tools |
|-------|-------|
| LLM | Ollama (local LLaMA, Mistral, Phi, etc.) |
| Planner | LangGraph, CrewAI |
| Memory | Redis, Weaviate, Qdrant |
| MCP Runtime | modelcontextprotocol/mcp-servers |
| MCP Servers | Filesystem, SQL, REST API, custom internal tools |
| Metadata / Catalog | DataHub, Amundsen, Atlan |
| Lineage | OpenLineage, Marquez |
| Data Virtualization | Trino, Dremio |
| Governance | OPA, Rego |
| IAM | Okta, AzureAD |
| Deployment | Docker Compose, Kubernetes, Backstage |

---

# Agent Lifecycle

- User/system triggers agent  
- Agent plans workflow (LangGraph)  
- Agent queries Fabric for:
-- Data discovery
-- Other agent discovery
-- Semantic definitions  
- Agent plans next actions  
- Agent uses MCP Runtime:
-- Access MCP Servers  
- Fabric tracks lineage:
-- Logs agent→data interaction  
- Agent returns response  
- Governance enforces policies & audits actions  

---

# Governance

✅ All agents and MCP runtimes use SSO-based identities (Okta, AzureAD)  
✅ Policy-as-code enforced via OPA / Rego  
✅ All MCP calls are logged  
✅ Full lineage maintained via OpenLineage  

---

# Use Cases

✅ AI-powered analytics  
✅ Process automation  
✅ Knowledge agents  
✅ Compliance-first AI  
✅ Composable AI products → domain agent marketplace  

---

# Future Directions

✅ Cross-domain agent-to-agent orchestration  
✅ Fabric-driven agent planning (semantic flow)  
✅ Automated lineage visualization  
✅ Open-source reference agents  
✅ Community-driven evolution  

---

# Attribution

**Author:** [Nihal Bhagchandani](https://github.com/NihalBhagchandani)  
**First published:** 8 June 2025  
**License:** Apache 2.0  

---

# Closing Vision

> The future of enterprise AI is not about monolithic copilots.  
> It’s about a **Mesh of domain-owned intelligence**, connected and governed by a **Fabric of data and semantics**, running **Agentic AI** on safe, composable, observable infrastructure.

---

