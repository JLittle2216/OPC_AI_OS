# 💎 OPC AI OS: The One-Person Company AI Operating System

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Model-Agnostic](https://img.shields.io/badge/Model-Agnostic-blue)](https://structurewebworks.com/blog/the-one-person-company-ai-operating-system)

The **OPC AI OS** is a high-fidelity, closed-loop business engine designed to eliminate "manual seams" in solo-entrepreneurship. By replacing traditional overhead (reception, dispatch, bookkeeping) with a specialized swarm of AI agents, it transforms the founder from a "doer" into a **Capital Allocator and System Orchestrator**.

## 🎯 The Vision: The Closed Loop
Most AI implementations are "point solutions" (e.g., a chatbot for leads). The OPC AI OS is a **systemic implementation** that connects the entire business lifecycle:

`Marketing` $\rightarrow$ `Intake` $\rightarrow$ `Sales` $\rightarrow$ `Operations` $\rightarrow$ `Finance` $\rightarrow$ `Growth`

When one layer completes its task, it triggers the next via a **Token-Based Handoff**, ensuring zero operational leakage.

---

## 🏗️ Core Architecture

### 👥 The Agent Swarm (43 Specialized Personas)
The system isn't one prompt; it's a hierarchy of specialized roles:
- **Layer 0: Orchestration** (CEO, State Manager, Quality Gatekeeper)
- **Layer 1: Marketing** (Ad Strategist, Content Engine, Brand Guardian)
- **Layer 2: Intake** (ICP Qualifier, Scheduling Coordinator)
- **Layer 3: Sales** (Solution Architect, Closing Assistant)
- **Layer 4: Operations** (Project Manager, Execution Monitor, Delivery Auditor)
- **Layer 5: Finance** (Invoicing Agent, Margin Analyst, Dynamic Pricing Optimizer)

### 📡 The Token Protocol
To maintain state without context drift, the system uses a formal **Handoff Payload**. Every transition includes:
- `token_id`: Unique lead/project identifier.
- `payload`: Critical data and pending actions.
- `heartbeat_timestamp`: A system-health check to prevent "frozen" tasks.

### 💾 The State Ledger
The OS is model-agnostic because it separates **Logic** from **State**.
- **Playbook (`PLAYBOOK.md`)**: The "Constitution" containing ICPs, pricing rules, and checklists.
- **Company State (`COMPANY_STATE.md`)**: The "Ledger" tracking all leads, projects, and financial snapshots in a structured JSON format.

---

## 🚀 Quick Start: Loading the OS

This system can be loaded into any advanced LLM (Claude, GPT, etc.) or agentic framework.

1. **Clone this Repo** or download the files.
2. **Prepare your State Files**: Create a `PLAYBOOK.md` and `COMPANY_STATE.md` (see `/schema` for the required format).
3. **Load the Spec**: Upload the `OPC_AI_OS_Master_Spec.md` to your AI's context.
4. **Initialize**: Use the following prompt:
   > *"Load the OPC AI OS Master Spec. Initialize the CEO / Orchestrator. Read the `PLAYBOOK.md` and `COMPANY_STATE.md`. Identify the current highest-priority token in the pipeline and suggest the next action."*

---

## 🛠️ Project Structure

```text
OPC_AI_OS/
├── OPC_AI_OS_Master_Spec.md  # Core System Instructions
├── topology/
│   └── agent_topology.md    # Map of the 43 specialized agents
├── protocols/
│   └── communication_protocol.md # Token-handoff & Heartbeat logic
├── schema/
│   └── global_data_schema.md # State & Playbook specifications
└── qa/
    ├── pressure_test_report.md # Stress test results
    └── architectural_patches.md # Hardening fixes
```

## 📜 License
Distributed under the MIT License. See `LICENSE` for more information.
