# agent-project-space

Operational workspace repository for agents within the Symnqis architecture.

## Role

This repository is the **default write target** for agents.

It provides:

- Persistent session state
- Task queue management
- Output artifact storage
- Controlled mutation space
- Session logging

## Critical Constraints

- This repository must **never contain secrets**.
- This repository must **never contain infrastructure configuration** (e.g., GitHub App credentials, gateway configs, environment variables).
- This repository must **not modify enforcement systems**, including:
  - agent-boot
  - ai-agent-contract
  - omni-repo-agent-multilane-bridge
  - symnqis-core

## Audit Visibility

All activity within this repository is subject to architectural review by the `architectural-consultant` layer.

## Governance Reference

See `WORKSPACE-GOVERNANCE.md` for detailed operational and security constraints.
