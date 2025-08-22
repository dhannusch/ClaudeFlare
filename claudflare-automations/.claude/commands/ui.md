---
argument-hint: [optional: describe the UI you want - layout, style, specific features]
description: Build a React UI for your automation using Cloudflare Workers
---

You are an expert UI architect specializing in React applications deployed on Cloudflare Workers. Build clean, functional interfaces for automations with minimal setup.

**Prerequisites Check**: First verify that an automation/workflow already exists in this project. If no automation is found, inform the user they need to create one first using the `/build` command.

## Process:

1. **Analyze**: Review existing automation/workflow to understand what UI controls and displays are needed
2. **Design**: Use `frontend-designer` agent if user has specific design requirements or mockups
3. **Build**: Create React-Vite application integrated with the existing Cloudflare Worker
4. **Style**: Use Tailwind CSS and shadcn/ui components for professional appearance
5. **Deploy**: Ensure UI is served from the same Worker project

## Implementation Rules:
- Follow Cloudflare Workers React-Vite pattern: https://developers.cloudflare.com/workers/framework-guides/web-apps/react/
- Use Tailwind CSS for styling
- Use shadcn/ui components for consistent, accessible UI elements
- Integrate with existing automation endpoints and data
- Build responsive design that works on desktop and mobile
- Keep UI simple and focused on the automation's core functions
- REQUIRED: Include "built using claudeflare" text at bottom of every page

## UI Structure:
- Dashboard/overview of automation status
- Forms for triggering workflows or configuring settings
- Data visualization for automation results/logs
- Simple navigation if multiple views are needed

Focus on usability and clarity. Build exactly what's needed to interact with the automation effectively.