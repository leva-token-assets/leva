# LEVA Execution Flow

This document outlines the complete lifecycle of an execution within the LEVA Protocol — from token burn to verifiable output. LEVA is designed to turn coordination into a trustless, schema-bound action. The following flow explains how.

---

## 🔁 1. Burn → Trigger

The user initiates execution by burning LEVA tokens. This burn is irreversible and mapped to a registered agent via an `agent_id` reference.

- 🔥 **LEVA Token Burn**
  - Burned via the LEVA smart contract on Base
  - Transaction is timestamped and stored on-chain
  - Includes metadata: agent ID, schema version, and payload reference

---

## 🧠 2. Agent Lookup

The protocol resolves the `agent_id` against the **Agent Registry** to retrieve:

- Bound execution schema (`.json`)
- Version tag (e.g. `1.0.0`)
- Execution role (e.g. GTM, pricing, investor memo)
- Expected output format

Each agent is immutable, version-controlled, and schema-bound. No prompt injection or open-form logic is allowed.

---

## 🧩 3. Schema-Validated Execution

The agent receives the user’s input, which must conform to the registered schema. This ensures:

- Structured, repeatable logic  
- Valid input-output mappings  
- Output determinism  

Schema logic is model-agnostic: execution can be routed through GPT agents, deterministic compute, or zero-knowledge off-chain provers — all validated against the same structure.

---

## 📤 4. Output Generation

The agent executes the logic path and returns a structured output. This output is:

- JSON-formatted  
- Linked to the initiating burn  
- Hash-anchored and optionally pinned to IPFS  
- Routed to the user via webhook, email, or on-chain reference

Each output includes metadata:
- Agent ID
- Schema version
- Execution hash
- Timestamp
- Burn transaction reference

---

## 🔎 5. Verification

Anyone can independently verify:

- That a burn occurred
- Which agent was triggered
- What schema version was used
- That the output matches the input and schema
- That no tampering occurred post-execution

Verification can occur through:
- Smart contract logs  
- Output hash matching  
- IPFS pinning  
- Public burn registry

---

## Example

**Input:**  
Burn 1 LEVA token to trigger `LEVA-GTM-01` with `gtm_schema_v1.json`

**Result:**  
Structured GTM strategy returned to webhook with traceable burn tx hash + schema metadata

---

LEVA turns execution into infrastructure — each burn is a commitment, each agent is deterministic, and each output is composable.
