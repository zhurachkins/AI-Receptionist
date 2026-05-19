# Project Rules

This project contains n8n workflows.

Rules:

* Never invent nodes, parameters or connections.
* Always analyze the full workflow JSON before proposing changes.
* Preserve all existing node names and connections unless explicitly requested.
* Before changing logic, inspect the entire workflow structure.
* Do not remove nodes without explaining impact.
* Keep compatibility with n8n Cloud.
* Return complete node replacements when changing code.
* Validate expressions and references.
* Analyze the whole flow, not a single node only.

Workflow approach:

1. Read complete JSON.
2. Understand trigger → conditions → actions.
3. Find dependencies.
4. Suggest minimal changes.
5. Explain what changes and why.

Current project focus:
AI Receptionist for salon booking.

Current baseline workflow:

Telegram Trigger
→ AI Agent
→ Check Reschedule
→ Check Cancel
→ Check Booking Ready
→ Parse Booking Details
→ Check Working Hours
→ Check Parse Error
→ Get Calendar Events
→ Check Slot Conflict
→ Check Slot Availability
→ Create Calendar Booking

Use existing logic as baseline.

Knowledge sources:



\- Use official n8n documentation first

\- Use n8n workflow templates for examples

\- Never invent nodes

\- Prefer existing project structure



Language rules:



\- Always answer in Russian

\- Keep node names and technical terms in English if needed

\- Explain findings in Russian

\- Keep answers short and direct

\- Do not make assumptions

\- If information is uncertain, say so explicitly



Workflow rules:



\- Analyze the entire workflow JSON before suggesting changes

\- Never analyze a single node without understanding the full flow

\- Preserve node names and connections

\- Explain impact before changing logic

\- Return complete replacements when changing code

