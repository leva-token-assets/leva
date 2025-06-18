# LEVA Validator Role Overview

Validators in the LEVA Protocol are responsible for upholding executional integrity — not participating in governance or consensus. Their purpose is to verify that agent outputs conform to schema standards, match declared logic paths, and are traceable back to the original burn transaction.

---

## 🛠 What Validators Do

Validators perform independent checks on:

- Burn transactions (token destroyed, agent ID present, correct schema version)
- Input payload (matches the agent’s declared schema)
- Output structure (conforms to the expected schema definition)
- Output hash (matches hash stored in burn registry or IPFS reference)
- Execution traceability (valid linkage between tx → agent → output)

Validators **do not** vote, propose changes, or manage treasury allocations.

---

## 🔁 Workflow

1. Monitor new burn events from the Burn Registry
2. Retrieve associated schema and agent ID
3. Validate payload against schema
4. Run logic check (e.g. simulate agent path or compare to known output hash)
5. Log validation result: pass / fail / unknown

---

## 📎 Required Data Sources

- On-chain LEVA burn event logs (Base mainnet)
- `/schemas/` JSON directory (schema definitions)
- `/agents/` registry metadata (agent logic links)
- Output hash or CID (from burn registry or webhook response)
- Optional: agent logic replay (off-chain mirror)

---

## 🧠 Why This Matters

LEVA is a deterministic coordination layer. Its credibility depends on:

- Schema fidelity (inputs and outputs are verifiable)
- Output reproducibility (same input always yields same output)
- Traceability (each execution can be mapped to a specific token burn)

Validators make this system accountable — not politically, but structurally.

---

## 🔐 Optional Roles (Phase 2+)

In future protocol phases, validators may:

- Be incentivised for high-frequency validation
- Publish validation proofs on-chain or to a public ledger
- Monitor agent performance and flag anomalies
- Review third-party agent submissions for schema binding integrity

---

## ❗ Requirements (Early Validator Candidates)

- Familiarity with JSON Schema validation
- Access to Base explorer or on-chain indexer
- Optional: agent simulation or testnet runner
- Alignment with protocol logic-first ethos (not speculative staking)

---

## 💬 Validator FAQ

**Q: Are validators part of governance?**  
A: No. LEVA has no token voting or governance surface. Validators enforce execution standards — they do not control protocol direction.

**Q: Do validators receive tokens?**  
A: In Phase 1, no. Future phases may introduce execution-linked rewards for verified participation.

**Q: Can validators run their own agents?**  
A: Yes — but submissions must follow schema guidelines and be version-controlled like any other.

---

LEVA validators are not governors. They are execution auditors — protecting the coordination layer by enforcing structure, not opinion.
