# Contributing to OPC AI OS

Thank you for your interest in evolving the One-Person Company AI Operating System! 

This is a living system. As AI capabilities expand and business models evolve, the OS must adapt.

## 🛠️ How to Propose Changes

### 1. Proposing a New Agent
If you identify a gap in the topology (e.g., a need for a "Tax Compliance Agent"):
- Define the agent's specific responsibility.
- Map which layer it belongs to.
- Define the **Handoff Trigger** (Who gives them the token?) and the **Handoff Condition** (When do they pass it?).

### 2. Updating the Playbook
If you find a more efficient "Standard Operating Procedure" (SOP):
- Document the new process.
- Run a "Pressure Test" simulation to ensure it doesn't create leaks in other layers.
- Propose the update to the `PLAYBOOK.md` structure.

### 3. Refining the Data Schema
If the `COMPANY_STATE.md` is missing critical data needed for an agent to function:
- Propose the new field in the `global_data_schema.md`.
- Ensure the field is JSON-compatible for cross-model portability.

## 🚨 Submission Process
1. Fork the repository.
2. Create a feature branch (`git checkout -b feature/new-agent`).
3. Commit your changes with a clear description of the "Business Value" added.
4. Open a Pull Request.
