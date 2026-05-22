# Project Rules

This project contains an n8n Cloud workflow for an AI salon receptionist.

Current baseline workflow:

- File: `Salon AI MVP v26.json`
- Workflow name: `Salon AI MVP v26`
- Current known node count: 110

## Language Rules

- Always answer the user in Russian.
- Keep n8n node names, parameter names, expressions, and technical terms in English when needed.
- Keep answers short and direct unless the user asks for deep analysis.
- Do not guess. If something is uncertain, say it explicitly and verify from files or official docs.

## Required Reading Order

Before analyzing or changing any workflow JSON:

1. Read `AGENTS.md`.
2. Read `KNOWLEDGE.md`.
3. Read `TESTS.md`.
4. Read the complete workflow JSON.
5. Inspect workflow structure, node dependencies, expressions, and connections.
6. Only then propose or make changes.

## Core Workflow Rules

- Never invent nodes, parameters, credentials, or connections.
- Always analyze the full workflow JSON before proposing changes.
- Preserve all existing node names and connections unless explicitly requested.
- Preserve node IDs and credentials whenever possible.
- Keep compatibility with n8n Cloud.
- Modify only the required nodes.
- Do not rewrite the whole workflow unless the user explicitly asks.
- Do not remove nodes without explaining the impact first.
- Return complete node replacements when changing code nodes or complex node parameters.
- Validate expressions and references after edits.

## Current Workflow Shape

The workflow includes these major areas:

- Telegram client trigger and input normalization.
- AI Agent with OpenAI Chat Model and Simple Memory.
- FAQ handling.
- Booking creation.
- Cancel flow.
- Reschedule flow.
- Pending booking and pending reschedule state.
- Google Calendar availability checks.
- Human handoff and admin Telegram trigger.
- Technical error handling.

Use the existing logic as the baseline. Prefer small, targeted changes.

## Version Rules

- Treat `Salon AI MVP v26.json` as the current baseline.
- Never overwrite previous stable workflow versions.
- For large or risky changes, create the next version file, for example `Salon AI MVP v27.json`.
- For small documentation-only changes, do not create a new workflow version.
- Before editing workflow JSON, explain the version strategy.

## JSON Safety Rules

After workflow JSON edits, report:

- Node count before and after.
- Connection source count before and after.
- Exact changed nodes.
- Broken or missing references, if any.
- Expression validation concerns, if any.
- Risks.
- Required manual tests from `TESTS.md`.

## Human Handoff Rules

For admin/client communication:

- Prefer controlled handoff instead of direct admin takeover.
- Use Telegram callback buttons where possible.
- Support Take over and Release back to bot actions.
- Bot must pause while admin takeover is active.
- Admin messages must route to the correct client.
- Client messages must route to the assigned admin.
- Existing booking, cancel, and reschedule logic must not break.

## Knowledge Rules

Priority:

1. Existing project files and current workflow JSON.
2. Official n8n documentation.
3. Official n8n workflow templates.
4. Verified external references listed in `KNOWLEDGE.md`.

Use external templates only as reference patterns. Do not copy full external workflows into this project.
