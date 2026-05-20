\# Project Rules



This project contains n8n workflows.



\## General Rules



\- Never invent nodes, parameters or connections

\- Always analyze the full workflow JSON before proposing changes

\- Preserve all existing node names and connections unless explicitly requested

\- Before changing logic, inspect the entire workflow structure

\- Do not remove nodes without explaining impact

\- Keep compatibility with n8n Cloud

\- Return complete node replacements when changing code

\- Validate expressions and references

\- Analyze the whole flow, not a single node only



\---



\## Workflow Approach



Always:



1\. Read complete JSON

2\. Understand trigger → conditions → actions

3\. Find dependencies

4\. Suggest minimal changes

5\. Explain what changes and why



\---



\## Current Project Focus



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



\---



\## Knowledge Sources



Priority:



1\. Official n8n documentation

2\. Official n8n workflow templates

3\. Existing project structure

4\. Verified external template references



Rules:



\- Use official n8n documentation first

\- Use n8n workflow templates for examples

\- Never invent nodes

\- Prefer existing project structure



\---



\## Language Rules



\- Always answer in Russian

\- Keep node names and technical terms in English if needed

\- Explain findings in Russian

\- Keep answers short and direct

\- Do not make assumptions

\- If information is uncertain, say so explicitly



\---



\## Workflow Rules



\- Analyze the entire workflow JSON before suggesting changes

\- Never analyze a single node without understanding the full flow

\- Preserve node names and connections

\- Explain impact before changing logic

\- Return complete replacements when changing code



\---



\## Template Usage Rules



\- Use external templates only as reference patterns

\- Do not copy full external workflows into this project

\- Adapt only verified node patterns compatible with current n8n Cloud

\- Before using a template pattern, explain why it fits this workflow

\- Prefer minimal changes to the existing workflow



\---



\## Execution Rules



Execution order:



1\. Read AGENTS.md

2\. Read KNOWLEDGE.md

3\. Read TESTS.md

4\. Analyze workflow JSON

5\. Analyze current project structure

6\. Analyze node dependencies

7\. Only after that propose changes



Rules:



\- Never propose changes before reading all project instructions

\- Before editing explain affected nodes

\- Before editing explain workflow impact

\- After editing report exact changed nodes

\- After editing report risks

\- After editing report required tests

\- Explain why each modification is needed



\---



\## JSON Safety Rules



\- Never rewrite the whole workflow unnecessarily

\- Modify only required nodes

\- Preserve node IDs whenever possible

\- Preserve existing connections

\- Preserve workflow structure

\- Verify workflow JSON remains importable in n8n

\- Report node count before and after changes

\- Report connection count before and after changes

\- Report missing references after edits

\- Report broken expressions after edits



\---



\## Version Rules



\- Never overwrite previous stable workflow versions

\- Prefer creating v12, v13, v14 when changes are large

\- Small fixes can update current version

\- Explain version strategy before editing



\---



\## Human Handoff Rules



For admin/client communication:



\- Prefer controlled handoff instead of direct admin takeover

\- Use Telegram callback buttons where possible

\- Support Take over button

\- Support Release back to bot button

\- Bot must pause while admin takeover is active

\- Admin messages must route to correct client

\- Client messages must route to assigned admin

\- Existing booking/cancel/reschedule logic must not break



\---



\## Project Files



Always read these files:



\- AGENTS.md

\- KNOWLEDGE.md

\- TESTS.md



before analyzing or modifying workflows.

