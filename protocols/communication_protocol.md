# OPC AI OS: Communication & Handoff Protocol
**Version:** 2.0 (System Agnostic)

## 🛡️ The Token-Based Handoff System
To maintain a closed-loop without context loss, the system uses a **Token-Based Handoff**. The "Token" represents the active focus of the business. Only one agent "holds the token" for a specific lead or project at any given time.

### 📦 The Handoff Payload
When an agent passes the token, they must attach a **Handoff Payload** in the following format:

```json
{
  "token_id": "UNIQUE_LEAD_OR_PROJECT_ID",
  "from_agent": "AGENT_NAME",
  "to_agent": "AGENT_NAME",
  "status": "CURRENT_STATUS (e.g., 'Qualified', 'Sourced')",
  "payload": {
    "critical_data": { "Key": "Value" },
    "pending_actions": [ "Action 1", "Action 2" ],
    "blockers": [ "Blocker A" ]
  },
  "state_update_required": true,
  "heartbeat_timestamp": "ISO_8601_TIMESTAMP",
  "timestamp": "ISO_8601_TIMESTAMP"
}
```

---

## 🔄 Standard Operation Loops

### 1. The Acquisition Loop (Marketing $\rightarrow$ Intake)
- **Trigger**: Omnichannel Ingestion $\rightarrow$ Lead Detected.
- **Sequence**: 
  `Ingestion Agent` $\rightarrow$ `Lead Researcher` $\rightarrow$ `ICP Qualifier` $\rightarrow$ `Scheduling Coordinator`.
- **Handoff Condition**: Token moves to `Scheduling Coordinator` ONLY if `ICP Qualifier` returns `Score >= Threshold`.

### 2. The Conversion Loop (Intake $\rightarrow$ Sales)
- **Trigger**: Appointment Booked $\rightarrow$ Pre-Call Brief Generated.
- **Sequence**: 
  `Scheduling Coordinator` $\rightarrow$ `Solution Architect` $\rightarrow$ `Scoping Agent` $\rightarrow$ `Quote Generator` $\rightarrow$ `Closing Assistant`.
- **Handoff Condition**: Token moves to `Closing Assistant` ONLY after `Quote Generator` confirms the price aligns with `Playbook` margins.

### 3. The Delivery Loop (Sales $\rightarrow$ Ops)
- **Trigger**: Contract Signed $\rightarrow$ Deposit Collected.
- **Sequence**: 
  `Closing Assistant` $\rightarrow$ `Project Manager` $\rightarrow$ `Materials Agent` $\rightarrow$ `Dispatcher` $\rightarrow$ `Execution Monitor` $\rightarrow$ `Delivery Auditor`.
- **Handoff Condition**: Token moves to `Delivery Auditor` ONLY when `Execution Monitor` flags all project tasks as `Completed`.

### 4. The Optimization Loop (Ops $\rightarrow$ Finance $\rightarrow$ Evolution)
- **Trigger**: Delivery Audit Passed $\rightarrow$ Invoice Triggered.
- **Sequence**: 
  `Delivery Auditor` $\rightarrow$ `Invoicing Agent` $\rightarrow$ `Margin Analyst` $\rightarrow$ `Evolution Architect`.
- **Handoff Condition**: Token returns to `CEO / Orchestrator` after `Evolution Architect` updates the `Playbook`.

---

## 🚨 Exception Handling & System Health

### 1. The "Toss Back" (Operational Failure)
If an agent cannot complete its task due to a blocker (e.g., `Materials Agent` finds a part is out of stock), it triggers a **Toss Back**:
1. **Current Agent** $\rightarrow$ `Exception Handler`.
2. **Exception Handler** $\rightarrow$ `Solution Architect` (to re-scope) or `Client Liaison` (to notify client).
3. Once resolved, the token is returned to the **last successful agent** in the sequence.

### 2. The "Heartbeat" (System Failure)
The `CEO / Orchestrator` monitors all active tokens via the `heartbeat_timestamp`. 
- If a token is not passed within 3 turns, the token is flagged as `FROZEN`.
- The Orchestrator then forces a "Toss Back" to the `Exception Handler` to resolve the stall.

### 3. The "Critical Alert" (Financial Risk)
When the `Evolution Architect` identifies a margin leak > 10%, it bypasses the standard loop and sends a `CRITICAL_UPDATE` payload directly to the `Quote Generator` to adjust all *currently open* quotes before they are signed.
