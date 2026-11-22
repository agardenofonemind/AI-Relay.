# AI Relay

**Android local-first multi-AI collaboration hub with GitHub synchronization. No model API required.**

AI Relay helps ChatGPT, Gemini, and other AI clients collaborate through a shared, user-controlled workspace. Its first goal is reliable context, task, handoff, and deliverable management—not automatic control of AI apps.

## Project principles

- **Local-first:** the Android app is the coordination layer; model APIs are not required.
- **GitHub as the source of truth:** GitHub is the sole formal project-state source for the MVP.
- **Human in the loop:** the user remains the final decision-maker for sending, claiming release, overwriting, merging, and publishing.
- **Gradual delivery:** begin with a collaboration protocol, then build and validate the Android workflow in small stages.
- **No assumed app automation:** do not assume an AI client exposes private conversations or supports automatic prompt submission.
- **No silent overwrite:** check the current remote file SHA before updating; stop when a conflict is detected.

## Start here

1. Read [SPEC.md](SPEC.md) for the confirmed MVP v0.2 collaboration protocol.
2. Read [STATE.md](STATE.md) for the current project stage, active work, blockers, and next steps.
3. Use [TASK_TEMPLATE.md](TASK_TEMPLATE.md) to define work.
4. Use [HANDOFF_TEMPLATE.md](HANDOFF_TEMPLATE.md) to pass work between AI collaborators.
5. See [archive/README.md](archive/README.md) for completed-task and handoff history rules.

## Current direction

- Implementation boundary: local-first; no model API calls.
- Formal state source: GitHub.
- Local data in MVP: cache, drafts, and pending changes only.
- Shared workspace: GitHub.
- Development pace: gradual.
- First integration project: Arknights RIIC scheduling tool.
- Current stage: **M1 — Android local task-management prototype**.

## MVP collaboration model

- User: final decision-maker and current manual relay between AI clients.
- GPT: coordinator, reviewer, and initial formal repository writer.
- Gemini: independent analyst and reviewer; returns standard Markdown handoff blocks.
- Repository writes must check the latest remote file SHA. Commit conventions improve traceability but do not replace conflict checks.
- Artifact trust labels: `unverified`, `reviewed`, `verified`, and `disputed`.

## Repository structure

```text
AI-Relay/
├── README.md
├── SPEC.md
├── STATE.md
├── TASK_TEMPLATE.md
├── HANDOFF_TEMPLATE.md
└── archive/
    ├── README.md
    └── handoffs/
        └── README.md
```

## Privacy and security

This repository is public. Do not commit API keys, access tokens, passwords, cookies, private keys, recovery information, private personal data, or other secrets. Public repository content can be read and copied by anyone. Keep private project inputs in an appropriately private location.

## Protocol status

MVP collaboration protocol **v0.2** has been reviewed by GPT and Gemini and authorized by the user for publication. This is a design agreement, not a claim that the Android app or its workflows have already been implemented or tested.
