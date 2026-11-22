# AI Relay

**Android local-first multi-AI collaboration hub with GitHub synchronization. No model API required.**

AI Relay aims to make ChatGPT, Gemini, and other AI clients collaborate through a shared, user-controlled workspace.

## Project principles

- **Local-first:** the Android app is the coordination layer; AI model APIs are not required.
- **GitHub as shared workspace:** tasks, handoffs, project state, and approved deliverables live in version control.
- **Human in the loop:** the user remains the final decision-maker for sending, overwriting, merging, and publishing.
- **Gradual delivery:** begin with a collaboration protocol, then build and validate the Android workflow in small stages.
- **No assumed app automation:** do not assume an AI client exposes private conversations or supports automatic prompt submission.

## Start here

1. Read [SPEC.md](SPEC.md) for the collaboration protocol.
2. Read [STATE.md](STATE.md) for current decisions, milestones, and next steps.
3. Use [TASK_TEMPLATE.md](TASK_TEMPLATE.md) to define work.
4. Use [HANDOFF_TEMPLATE.md](HANDOFF_TEMPLATE.md) to pass work between AI collaborators.

## Current direction

- Implementation boundary: local-first; no model API calls.
- Shared workspace: GitHub.
- Development pace: gradual.
- First integration project: Arknights RIIC scheduling tool.

## Repository structure

```text
AI-Relay/
├── README.md
├── SPEC.md
├── STATE.md
├── TASK_TEMPLATE.md
└── HANDOFF_TEMPLATE.md
```

The structure will expand as the workflow is tested and the Android prototype takes shape.

## Privacy and security

This repository is public. Do not commit API keys, access tokens, passwords, cookies, private personal data, or other secrets. Public repository content can be read and copied by anyone. Keep private project inputs in an appropriately private location.

## Status

The project is in **M0 — collaboration protocol setup**. The protocol is a draft and should be reviewed by both AI collaborators and confirmed by the user before it is treated as stable.
