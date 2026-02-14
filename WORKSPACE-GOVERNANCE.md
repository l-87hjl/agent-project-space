# WORKSPACE GOVERNANCE

This document defines operational and security constraints for the agent-project-space repository.

## 1. Purpose

agent-project-space is the designated operational workspace for agents.

It is the only repository intended for routine write activity during normal agent execution.

---

## 2. Allowed Activities

Agents MAY:

- Update `agent/STATE.json`
- Update `agent/TODO.json`
- Append to `CHANGELOG.md`
- Write artifacts to `outputs/`
- Use `scratch/` for temporary files

---

## 3. Prohibited Content

The following must never exist in this repository:

- GitHub App credentials
- Private keys
- API tokens
- Environment configuration files
- Gateway configuration
- Infrastructure deployment files

This repository is not an infrastructure layer.

---

## 4. Enforcement Boundary

Agents must not:

- Modify execution gateways
- Modify boot contracts
- Modify governance contracts
- Modify core substrate repositories
- Attempt to change permission boundaries

Enforcement authority resides outside this repository.

---

## 5. Audit and Visibility

All writes within this repository are subject to review by the architectural-consultant layer.

Logs and state updates must be structured, transparent, and append-only where applicable.

---

## 6. Separation of Powers

This repository provides controlled mutation space without structural authority.

Governance resides in ai-agent-contract.
Execution authority resides in omni-repo-agent-multilane-bridge.
Audit authority resides in architectural-consultant.

Violation of these boundaries constitutes architectural drift.
