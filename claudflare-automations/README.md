# ClaudeFlare Automations

Build workflows and automations faster than n8n using Claude Code and Cloudflare's developer platforms (Workers, D1, KV, Workflows, Agents, Queues, etc.).

## Getting Started

This project is designed to work seamlessly with Claude Code. Simply describe what automation you want to build and let Claude handle the implementation.

### Quick Commands

- `/build [your automation idea]` - Create a new workflow or automation
- `/ui [optional styling preferences]` - Add a React UI to your existing automation

### Examples

```
/build Send a Slack notification whenever a new GitHub issue is created
/build Process CSV files uploaded to a webhook and store results in a database
/build Monitor RSS feeds and send email summaries daily
```

After building an automation, enhance it with a UI:
```
/ui Create a dashboard to monitor automation status
/ui Build a form to manually trigger the workflow
```

## Architecture

- **Runtime**: Cloudflare Workers for global edge deployment
- **API**: Hono framework for clean, fast APIs  
- **UI**: React + Vite served directly from Workers
- **Storage**: Cloudflare D1, KV, and other services as needed
- **Styling**: Tailwind CSS with shadcn/ui components

Claude Code automatically selects the optimal Cloudflare services for your specific use case. 
