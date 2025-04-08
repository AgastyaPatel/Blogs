---
title: "MCP Model Context Protocol"
author: "Agastya Patel"
date: "2025-03-12"
date-modified: "2025-03-12"
categories: [Notes, AI, MCP]
draft: false
---

Notes about the MCP Model Context Protocol.

## What is MCP?
Model Context protocol MCP is standard protocol which is used to connects different AI agents to external tools and services.

https://www.anthropic.com/news/model-context-protocol

## API vs MCP
Generally external services are connected using API which differs from providers to providers.
It's a pain to manage differnet API follow different SDKs, documentation, auth setup and maintaining them.

MCP is open standard which is being quickly adopted by many product developers, companies and organizations.

# MCP Features
- Single Protocol: Universal connector to integrate any service or tool.
- Dynamic Discovery: Automatically discover and connect to new tools. (similar to package managers)
- Two-way Communication: Agents can send (trigger events) and receive messages to and from external tools at the same time.

# MCP Components
MCP Host: Claude desktop or AI driven IDE which requires external tools to be connected to it.
MCP Client: External tool or service which is connected to MCP server.
MCP Servers: Lightweight servers which are used to connect MCP clients to MCP host.
Local Data Source: Local files, databases, etc.
Tool/Services: APIs of external tools and services.

_Just checkout the list of MCP servers and integrations below._
https://github.com/modelcontextprotocol/servers?tab=readme-ov-file








