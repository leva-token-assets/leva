# Agent Author Guide

This guide outlines how to create and submit new agents to the LEVA Protocol. Agents are deterministic logic paths tied to schemas and triggered by irreversible token burns. Every agent in the registry must meet strict structural, composability, and versioning standards.

---

## 🧠 What Is an Agent?

An agent is a machine-executable module that performs a defined logic function (e.g. pricing analysis, investor memo generation, GTM strategy mapping). It must:

- Be tied to a specific schema version (`.json`)
- Produce structured, JSON-formatted outputs
- Return predictable, reproducible results
- Operate independently of user interface or prompt injection

Agents are not GPT wrappers — they are schema-bound execution units that can be audited, forked, and composed.

---

## 🧩 Required Components

Each agent submission must include:

1. **Agent Metadata** (`agents/your_agent_name.md`)
   - Agent ID (e.g. `LEVA-INVEST-02`)
   - Version (`1.0.0`)
   - Description of logic path
   - Linked schema name and version
   - Tags (e.g. `funding`, `risk`, `positioning`)

2. **Linked Schema File** (`schemas/your_schema_name.json`)
   - Fully defined JSON schema  
   - Required fields clearly marked  
   - Example inputs and outputs recommended

3. **Execution Path Description**
   - How the agent uses the schema fields
   - What logic it applies
   - What the expected output structure looks like

4. **Optional Output Sample**
   - Realistic example of what this agent returns
   - Format: `output-examples/your_agent_output.json`

---

## 🧾 Naming Standards

- Agent ID: `LEVA-<DOMAIN>-<NN>` (e.g. `LEVA-RISK-04`)
- Schema file: lowercase, underscore-separated (e.g. `risk_exposure_schema_v1.json`)
- Versioning must follow semantic versioning (`v1.0.0`, `v1.1.0`, etc.)

---

## 🔁 Version Control

All agents must declare their version. New logic paths require:

- New schema version (if fields change)
- New agent ID (if execution logic diverges)
- Registry update to reflect upgrade path

Previous agent versions remain frozen and executable for transparency and auditability.

---

## ✅ Submission Criteria

Agents must:

- Be schema-bound  
- Pass JSON schema validation  
- Produce consistent outputs from matching inputs  
- Be composable and deterministic  
- Not rely on UI or user prompt context

---

## 🚀 How to Submit

Fork the repo or open a PR including:

- `agents/<your_agent>.md`  
- `schemas/<your_schema>.json`  
- (Optional) `output-examples/<your_agent_output>.json`  

Include a commit message:  
`Add new agent: LEVA-RISK-04 — maps operational risk from structured inputs`

All submissions will be reviewed by the protocol maintainers or validator mesh for schema validity and execution determinism.

---

Agents are not apps. They are modular execution paths — and they are what makes LEVA programmable.
