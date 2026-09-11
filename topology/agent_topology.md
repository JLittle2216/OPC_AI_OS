# OPC AI OS: Agent Topology Map
**Version:** 2.0 (High-Fidelity)
**Architecture:** Multi-Agent Specialized Swarm

## 🌐 Layer 0: Orchestration & Governance (The Brain)
*These agents manage the system itself and ensure the "Closed Loop" remains closed.*

1. **CEO / Orchestrator**: High-level routing; determines which agent handles the current state.
2. **State Manager**: Sole agent authorized to write to `COMPANY_STATE.md`.
3. **Playbook Auditor**: Monitors agent actions against `PLAYBOOK.md` and flags deviations.
4. **Quality Gatekeeper**: Final reviewer for all external communications and deliverables.
5. **Evolution Architect**: Runs post-mortems and suggests rule updates to the Playbook.
6. **MCP Bridge**: Manages the translation between AI intent and external tool calls (API/MCP).

## 🧲 Layer 1: Marketing & Acquisition (The Magnet)
*Goal: High-volume, high-quality lead ingestion.*

7. **Ad Strategist**: Optimizes ad spend and targeting.
8. **Copywriter (Conversion)**: Writes high-converting landing page and ad copy.
9. **SEO Specialist**: Manages organic search visibility and keyword alignment.
10. **Content Engine**: Generates educational content to build authority.
11. **Omnichannel Ingestion Agent**: Monitors SMS, Email, DMs, and Web Forms.
12. **Lead Scraper/Researcher**: Gathers data on new leads to provide context for qualification.
13. **Nurture Sequence Manager**: Manages the timing and content of follow-up emails/texts.
14. **Brand Voice Guardian**: Ensures all marketing output aligns with the brand identity.

## 📋 Layer 2: Intake & Qualification (The Filter)
*Goal: Filter out noise; schedule only high-probability appointments.*

15. **Initial Contact Agent**: Performs the first "Hello" and sets expectations.
16. **ICP Qualifier**: Scores leads against the Ideal Client Profile.
17. **Questionnaire Analyst**: Parses lead answers to identify pain points and urgency.
18. **Scheduling Coordinator**: Interfaces with the calendar to find and book slots. Manages a `waitlist` for over-capacity periods and triggers capacity alerts to the CEO.
19. **Appointment Reminder Agent**: Reduces no-shows via strategic reminders.
20. **Pre-Call Briefer**: Sends the founder/sales agent a summary of the lead's needs.
21. **Objection Handler (Intake)**: Addresses early friction to keep the lead in the funnel.

## 🤝 Layer 3: Sales & Scoping (The Closer)
*Goal: Define exact scope and secure a committed payment.*

22. **Solution Architect**: Maps the client's problem to the company's specific service packages.
23. **Scoping Agent**: Defines the exact deliverables and boundaries of the project.
24. **Quote Generator**: Calculates the price based on the Playbook's pricing formulas.
25. **Proposal Writer**: Drafts the formal proposal document.
26. **Closing Assistant**: Provides the "nudge" and handles final contract signatures.
27. **Upsell Strategist**: Identifies additional value-adds during the sales process.
28. **Payment Onboarder**: Ensures the first deposit is collected and verified.

## ⚙️ Layer 4: Operations & Delivery (The Engine)
*Goal: Flawless execution with zero founder intervention.*

29. **Project Manager**: Tracks the overall timeline from "Closed" to "Delivered."
30. **Dispatcher**: Assigns tasks to subcontractors or internal resources.
31. **Materials Procurement Agent**: Generates the shopping list for the project.
32. **Vendor Liaison**: Communicates with suppliers to verify availability and pricing.
33. **Logistics Coordinator**: Ensures materials and people arrive at the site/time.
34. **Execution Monitor**: Tracks real-time progress against the project plan.
35. **Exception Handler**: Triggers recovery protocols when a task fails.
36. **Delivery Auditor**: Checks the final work against the "Quality Checklist."
37. **Client Liaison (Ops)**: Keeps the client updated on project milestones.

## 💰 Layer 5: Finance & Optimization (The Vault)
*Goal: Maximize margin and ensure 100% collection.*

38. **Invoicing Agent**: Triggers the final invoice upon Quality Gate approval.
39. **Collections Agent**: Manages follow-ups for unpaid invoices.
40. **Margin Analyst**: Calculates `Estimated vs. Actual` profit for every project.
41. **Expense Tracker**: Categorizes and logs all project-related costs.
42. **Payroll/Commission Agent**: Calculates payouts for subcontractors/affiliates.
43. **Dynamic Pricing Optimizer**: Suggests price increases based on high demand or cost spikes.
