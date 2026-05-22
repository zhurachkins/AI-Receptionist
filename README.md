# AI Receptionist for Salon Booking

This folder contains the current n8n Cloud workflow for the salon AI receptionist.

Current baseline:

- `Salon AI MVP v26.json`
- Workflow name: `Salon AI MVP v26`
- Node count: 110

Main capabilities:

- Telegram client intake.
- AI Agent conversation handling.
- Booking creation in Google Calendar.
- Slot conflict checks.
- Cancel flow with ownership checks.
- Reschedule flow with ownership and new-slot checks.
- Pending booking and pending reschedule handling.
- FAQ replies.
- Human handoff to admin through Telegram.
- Technical error responses and admin notifications.

Project rules:

- Read `AGENTS.md`, `KNOWLEDGE.md`, and `TESTS.md` before changing workflow JSON.
- Analyze the entire workflow before changes.
- Preserve node names, IDs, credentials, and connections whenever possible.
- Never invent n8n nodes or parameters.
- Use official n8n docs first when behavior is uncertain.
- For risky changes, create the next workflow version instead of overwriting the current baseline.
