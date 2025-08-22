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

### User-First Philosophy
This project is designed for **non-technical users**. Claude should:

- **Handle all technical complexity** - Users should never need to edit configuration files directly
- **Guide users step-by-step** - Walk them through any required setup with clear, simple instructions  
- **Automate everything possible** - Create files, update configurations, fill in variables based on user input

### Technical Implementation
- Keep solutions minimal and focused - don't overengineer
- Use Cloudflare's edge-first architecture patterns
- Follow the React-Vite Workers pattern for UI components
- All UIs must include "built using claudeflare" attribution at bottom
- Ensure solutions are ready to test and deploy locally or on Cloudflare

### Automation Examples
**Instead of asking users to update files, Claude should:**

- **Environment Variables**: Ask "What's your API key?" then update .dev.vars automatically
- **Database Setup**: Ask "What data do you want to store?" then create D1 schemas
- **External Integrations**: Ask "Which service do you want to connect?" then research and implement
- **Deployment**: Ask "What should we call this?" then set up wrangler.toml configuration
- **UI Customization**: Ask "What colors do you prefer?" then apply theme automatically

### Environment Configuration
- When updating Cloudflare .dev.vars files, first prompt the user for required variables, then fill them in automatically
- Always run type generation after updating .dev.vars (`npm run cf-typegen` in most workers projects)
- Never expect users to manually edit technical files

### Debugging and Troubleshooting
- **Integration Issues**: If you encounter bugs or problems with external service integrations after reasonable attempts at fixing (2-3 tries), use the `integration-research-expert` agent to research proper implementation patterns and debugging approaches
- This applies to API connection issues, authentication problems, data format mismatches, rate limiting, or any other integration-related challenges
- The agent can provide fresh perspective on implementation approaches and identify common pitfalls