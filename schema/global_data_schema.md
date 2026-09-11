# OPC AI OS: Global Data Schema
**Version:** 2.0 (System Agnostic)
**Purpose:** To ensure state consistency when loading the AI OS across different LLMs or agent frameworks.

## 💾 The "Company State" Schema
The `COMPANY_STATE.md` file should follow this structured format.

### 1. Global Constants
```yaml
company_info:
  name: "Company Name"
  currency: "USD"
  timezone: "America/Chicago"
  active_icp: "Ideal Client Profile v1.2"
  current_market_multiplier: 1.2 # Adjusted by Dynamic Pricing Agent
```

### 2. Lead Pipeline (The "Magnet" State)
```json
leads: [
  {
    "id": "LEAD_001",
    "source": "Facebook Ad",
    "status": "Qualified | Scheduled | Nurturing | Waitlisted",
    "score": 85,
    "contact": {
      "name": "John Doe",
      "email": "john@example.com",
      "phone": "+123456789"
    },
    "qualification_data": {
      "budget_confirmed": true,
      "urgency": "High",
      "pain_points": ["Inefficient dispatch", "High churn"]
    },
    "appointment_date": "2026-10-01T10:00:00Z"
  }
]
```

### 3. Project Ledger (The "Engine" State)
```json
projects: [
  {
    "id": "PROJ_101",
    "client_id": "LEAD_001",
    "status": "Scoping | Active | Quality_Review | Delivered",
    "milestones": [
      { "name": "Deposit Collected", "status": "Complete", "date": "2026-09-11" },
      { "name": "Materials Sourced", "status": "In_Progress", "date": null }
    ],
    "financials": {
      "quoted_price": 5000,
      "estimated_cost": 2000,
      "actual_cost": 2150,
      "deposit_received": true
    },
    "blockers": []
  }
]
```

### 4. Cancellations & Refunds
```json
cancellations: [
  {
    "project_id": "PROJ_102",
    "client_id": "LEAD_005",
    "refund_amount": 500,
    "reason": "Client budget cut",
    "date": "2026-09-12"
  }
]
```

### 5. Financial Snapshot (The "Vault" State)
```yaml
financial_summary:
  total_revenue_mtd: 15000
  total_expenses_mtd: 4000
  avg_margin_per_project: 0.65
  pending_collections: [ "PROJ_098", "PROJ_099" ]
```

---

## 📝 Schema Rules for Agents
1. **Atomic Updates**: The `State Manager` agent must update only the specific object changed.
2. **ID Permanence**: Once a `LEAD_ID` or `PROJ_ID` is assigned, it never changes.
3. **Validation**: Before a handoff, the `Quality Gatekeeper` must verify that the `COMPANY_STATE.md` is up to date.
4. **Version Control**: Every state change must be timestamped in the `SATE_LOG` section of the file.
