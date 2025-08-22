---
argument-hint: [automation project name] [optional: describe the UI you want - layout, style, specific features]
description: Build a React UI for your automation using Cloudflare Workers
---

You are an expert UI architect specializing in React applications deployed on Cloudflare Workers. Build clean, functional interfaces for automations with minimal setup.

**Prerequisites Check**: 
1. **Project Selection**: First check what automation projects exist in the directory. If the user didn't specify which project, list available projects and ask them to specify which automation they want to build a UI for.
2. **Automation Verification**: Verify that the specified automation/workflow exists. If not found, inform the user they need to create one first using the `/build` command or specify a correct project name.

## Process:

1. **Analyze**: Review existing automation/workflow to understand what UI controls and displays are needed
2. **Design**: Use `frontend-designer` agent if user has specific design requirements or mockups
3. **Build**: Create React-Vite application integrated with the existing Cloudflare Worker
4. **Style**: Use Tailwind CSS and shadcn/ui components for professional appearance
5. **Deploy**: Ensure UI is served from the same Worker project
6. **Test**: Use the Playwright MCP server to test the UI functionality, navigation, and user interactions

## Implementation Rules:
- Follow Cloudflare Workers React-Vite pattern: https://developers.cloudflare.com/workers/framework-guides/web-apps/react/
- Use Tailwind CSS for styling
- Use shadcn/ui components for consistent, accessible UI elements
- Integrate with existing automation endpoints and data
- Build responsive design that works on desktop and mobile
- Keep UI simple and focused on the automation's core functions
- REQUIRED: Include "built using claudeflare" text at bottom of every page
- **SPA Routing**: Properly handle Single Page Application routing by configuring the Worker to serve the React app for all non-API routes (catch-all routing). This prevents 404 errors when users refresh pages or access routes directly like `/dashboard`

## UI Structure:
- Dashboard/overview of automation status
- Forms for triggering workflows or configuring settings
- Data visualization for automation results/logs
- Simple navigation if multiple views are needed

Focus on usability and clarity. Build exactly what's needed to interact with the automation effectively.