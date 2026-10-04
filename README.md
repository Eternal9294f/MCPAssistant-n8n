# n8n-mcp-ai-assistant
An AI assistant built with n8n that connects to external tools through MCP, enabling natural-language interaction with services such as Google Drive, Gmail, and GitHub.

# MCP Assistant

An AI-powered conversational assistant built with n8n that uses the Model Context Protocol (MCP) to connect an AI agent with external tools.

## Overview

MCP Assistant demonstrates how an AI agent can interact with external services through MCP.

The system consists of two connected workflows:

1. MCP Server
2. MCP Client

The MCP Server exposes tools, while the MCP Client connects those tools to an AI-powered conversational interface.

## Architecture

User
↓
Chat Interface
↓
AI Agent
↓
MCP Client
├── Custom MCP Server
│   ├── Google Drive
│   └── Gmail
│
└── GitHub MCP

## MCP Server

The MCP Server is an n8n workflow that exposes Google Drive and Gmail capabilities as tools through an MCP endpoint.

The production MCP endpoint is then consumed by the MCP Client.

## MCP Client

The MCP Client provides the conversational interface.

When a user sends a message, the AI Agent determines how to respond and can use connected MCP tools when required.

The client connects to:

- The custom MCP Server
- GitHub's MCP endpoint

## Key Features

- Conversational AI interface
- MCP-based tool integration
- Google Drive access
- Gmail access
- GitHub MCP integration
- AI agent
- Persistent conversation memory

## Tech Stack

- n8n
- Model Context Protocol (MCP)
- AI Agent
- OpenAI
- Google Drive
- Gmail
- GitHub MCP

## Workflow Structure

### MCP Server

`workflows/MCPServer.json`

Exposes Google Drive and Gmail as MCP tools.

### MCP Client

`workflows/MCPClient.json`

Connects the AI agent to MCP-based tools and provides the conversational interface.

## Product Perspective

The project explores how AI assistants can move beyond generating text and interact with external systems through standardized tool interfaces.

The architecture separates the tool layer from the conversational layer, making it possible to connect the AI agent to multiple external capabilities.

## Note

This repository contains exported n8n workflows.

Credentials, API keys, OAuth tokens, production endpoints, and other sensitive configuration should be configured separately inside n8n and should not be committed to the repository.
