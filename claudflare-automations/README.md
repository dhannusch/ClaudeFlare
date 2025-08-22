# ClaudeFlare Automations

Build workflows and automations faster than n8n using Claude Code and Cloudflare's developer platforms (Workers, D1, KV, Workflows, Agents, Queues, etc.).

## Getting Started

### Setup

1. Clone the repository and navigate to this project:
   ```bash
   git clone https://github.com/dhannusch/ClaudeFlare.git
   cd ClaudeFlare/claudflare-automations
   ```

2. Set up Cloudflare (if you haven't already):
   - Create a free Cloudflare account at [cloudflare.com](https://cloudflare.com)
   - Follow the [Cloudflare Workers getting started guide](https://developers.cloudflare.com/workers/get-started/guide/) to install Wrangler CLI and authenticate

3. Start Claude Code:
   ```bash
   claude
   ```
   
   **Optional - Skip Permission Checks**: For faster development without permission prompts (use at your own risk):
   ```bash
   claude --dangerously-skip-permissions
   ```

### Usage

This project is designed to work seamlessly with Claude Code. Simply describe what automation you want to build and let Claude handle the implementation.

### Quick Commands

- `/build [your automation idea]` - Create a new workflow or automation
- `/ui [project-name] [optional styling preferences]` - Add a React UI to your existing automation

### Examples

```
/build Send a Slack notification whenever a new GitHub issue is created
/build Process CSV files uploaded to a webhook and store results in a database
/build Monitor RSS feeds and send email summaries daily
```

After building an automation, enhance it with a UI (specify the project name):
```
/ui slack-form-automation Create a dashboard to monitor automation status
/ui github-webhook-automation Build a form to manually trigger the workflow
```

## Architecture

- **Runtime**: Cloudflare Workers for global edge deployment
- **API**: Hono framework for clean, fast APIs  
- **UI**: React + Vite served directly from Workers
- **Storage**: Cloudflare D1, KV, and other services as needed
- **Styling**: Tailwind CSS with shadcn/ui components

Claude Code automatically selects the optimal Cloudflare services for your specific use case. 
