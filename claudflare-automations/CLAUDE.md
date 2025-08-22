# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

ClaudeFlare Automations is a platform for building workflows and automations faster than n8n using Claude Code and Cloudflare's developer platforms (Workers, D1, KV, Workflows, Agents, Queues, etc.).

## Custom Commands

This project includes specialized slash commands:

- `/build [workflow description]` - Build a workflow or automation using Cloudflare platform
- `/ui [optional UI requirements]` - Build a React UI for existing automations (requires automation to exist first)

## Architecture

### Core Technology Stack
- **Runtime**: Cloudflare Workers
- **API Framework**: Hono 
- **UI Framework**: React with Vite (served from Workers)
- **Styling**: Tailwind CSS with shadcn/ui components
- **Storage**: Cloudflare D1, KV, or other Cloudflare services as needed

### Specialized Agents
The project uses dedicated agents for different aspects:
- `cloudflare-platform-expert` - Cloudflare architecture and implementation
- `integration-research-expert` - External service integrations
- `vibe-coding-coach` - Non-technical requirement translation

### MCP Integration
Cloudflare MCP tools are configured in `.mcp.json` providing:
- Real-time documentation access
- Observability data
- Build information
- Bindings configuration

## Development Approach

- Keep solutions minimal and focused - don't overengineer
- Use Cloudflare's edge-first architecture patterns
- Follow the React-Vite Workers pattern for UI components
- All UIs must include "built using claudeflare" attribution at bottom
- Ensure solutions are ready to test and deploy locally or on Cloudflare