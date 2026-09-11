# OPC AI OS: Architectural Patches (Hardening)
**Version:** 2.1
**Status:** Proposed for Implementation

## 🛠️ Patch 1: The "Reverse Motion" State (Fixes Scenario 1)
**Modification**: Update `Global Data Schema`.
- **Addition**: Add a `cancellations` object to `COMPANY_STATE.md`.
- **Logic**: When a project is cancelled, the `State Manager` moves the project from `projects` to `cancellations` and records the `refund_amount` and `reason`. This prevents "ghost projects" from skewing margin analysis.

## 🛠️ Patch 2: The "Buffer & Waitlist" Logic (Fixes Scenario 2)
**Modification**: Update `Agent Topology` (Scheduling Coordinator).
- **Addition**: Implement a "Waitlist" status in the Lead Pipeline.
- **Logic**: If `Calendar_Availability == 0` for the requested window, the `Scheduling Coordinator` moves the lead to `waitlist` and triggers a "Priority Notification" to the `CEO / Orchestrator` to consider expanding capacity or adjusting prices.

## 🛠️ Patch 3: The "Heartbeat" Protocol (Fixes Scenario 3)
**Modification**: Update `Communication Protocol`.
- **Addition**: Add a `heartbeat_timestamp` to every Handoff Payload.
- **Logic**: The `CEO / Orchestrator` monitors all active tokens. If a `heartbeat_timestamp` exceeds 3 turns without a handoff, the token is flagged as `FROZEN`. The Orchestrator then forces a "Toss Back" to the `Exception Handler`.

## 🛠️ Patch 4: The "Fast-Track" Evolution Path (Fixes Scenario 4)
**Modification**: Update `Communication Protocol`.
- **Addition**: Create a "Critical Alert" channel.
- **Logic**: When the `Evolution Architect` identifies a margin leak > 10%, it bypasses the standard loop and sends a `CRITICAL_UPDATE` payload directly to the `Quote Generator` to adjust all *currently open* quotes before they are signed.

## 🛠️ Patch 5: The "Model-Agnostic" Voice Guide (Fixes Scenario 5)
**Modification**: Update `PLAYBOOK.md` structure.
- **Addition**: Create a `Voice & Tone Constraints` section.
- **Logic**: Use "Positive and Negative" constraints (e.g., "ALWAYS use active voice; NEVER use corporate jargon like 'synergy'"). This forces different models (Claude vs GPT) to converge on the same brand output.
