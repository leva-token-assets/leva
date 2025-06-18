# LEVA Protocol – Frequently Asked Questions (FAQ)

This document outlines frequently asked questions about the LEVA Protocol — including how it works, what’s real at launch, and what’s coming in future phases.

---

## 🔥 What is LEVA?

LEVA is a coordination protocol that turns strategic execution into an on-chain primitive.  
It allows users to **burn tokens to trigger agents** — structured, schema-bound logic paths that return verifiable outputs. Each burn is permanent, traceable, and triggers action — not governance.

---

## 🚀 What happens when I burn a LEVA token?

A burn initiates a deterministic execution path:

1. You specify an `agent_id` (e.g. GTM strategy, investor memo)
2. The burn is recorded on-chain (Base network)
3. The selected agent is triggered
4. Your input is validated against a schema
5. The agent runs its logic and returns a structured output (JSON)
6. Output is hashed, logged, and optionally pinned to IPFS or routed to a webhook

Nothing is theoretical. The contracts, schemas, and agent registry are real.

---

## 🧠 What do LEVA agents actually do?

Each agent performs a specific strategic function — such as:

- Mapping go-to-market plans  
- Generating investor memos  
- Performing pricing diagnostics  
- Surfacing operational risks  
- Positioning companies against market categories

Agents are not free-form GPT prompts. They are **version-controlled, schema-bound execution units** that follow strict logic rules and return structured, reproducible outputs.

---

## 🔁 Is this AI?

Yes — but not as a product layer.  
LEVA encodes AI reasoning as **deterministic infrastructure**. Agents may be powered by LLMs (e.g. GPT), but the protocol does not depend on any one provider. It is **model-agnostic** and executes logic based on schema inputs — not prompt hacks or UI overlays.

OpenAI’s agent architecture (e.g. function calling) influenced LEVA’s schema design, but the system abstracts the model layer entirely.

---

## 💡 What is actually live at launch?

Phase 1 includes:

- Deployed LEVA token (Base mainnet)  
- Burn registry smart contract  
- Agent registry (off-chain, schema-bound)  
- Multiple functional agents with execution logic  
- Sample outputs routed via webhook/IPFS  
- Internal execution testbed (Eleva OS) with >5,700 activations  
- GitHub repo with agent, schema, and burn logic transparency

Smart contracts and registries are deployed and ready. Burn-to-output is real.

---

## 🧪 Are burns simulated or real?

Burns in Phase 1 are **real and irreversible**.  
LEVA tokens are sent to a non-recoverable address, and execution is triggered as a consequence. You can verify the burn transaction and the agent it triggered via on-chain logs and the burn registry.

---

## 🧾 How is execution priced?

Each burn represents one execution.  
There is **no staking, no yield farming, no passive economics**. The LEVA token has only one utility: to trigger logic.

- One token = one agent trigger  
- The token is consumed  
- The output is generated and stored  
- Supply decreases with every use

---

## 🧱 What makes LEVA different from typical AI tools or DAOs?

LEVA is not a product.  
It is not a chatbot, not a front-end, and not a dashboard.

It is:

- Deterministic: each burn produces a traceable output  
- Schema-bound: agents follow structured input/output logic  
- Verifiable: outputs can be proven via hash, timestamp, and registry  
- Non-governance: there is no token voting, no DAO surface  
- Executable: logic doesn’t live in slides or prompts — it runs

Execution becomes a protocol-level commitment, not a PowerPoint deliverable.

---

## 📦 How are schemas used?

Every agent is bound to a versioned schema — a strict JSON format defining inputs and outputs.

This ensures:

- No ambiguous prompts  
- No non-reproducible outputs  
- Logic paths can be tested and validated  
- External agents can integrate without coordination risk

Schemas are stored publicly and versioned immutably.

---

## 🧩 Can I build on LEVA?

Yes. The system is composable.  
You can:

- Submit new agents (with versioned schemas)  
- Reference existing agents in your own apps  
- Trigger execution via webhook  
- Watch burns on-chain and route outputs to other systems

SDKs and more flexible integrations are coming in Phase 2.

---

## 🔐 Who verifies execution?

In Phase 1, execution is deterministic and logged — but not yet externally validated.  
In Phase 2, **validators** will be able to independently verify:

- That the output matches the schema  
- That the hash matches the burn  
- That the agent executed the correct logic path

Validators do not govern. They **enforce schema integrity** and execution traceability.

---

## 🌐 What’s the broader vision?

LEVA aims to make **execution programmable** — not through workflows, but through infrastructure.

- Every strategy becomes a trigger  
- Every action is logged  
- Every output is composable  
- And every execution burns a token — turning logic into consequence

---

## 💬 Who is this for?

LEVA is built for:

- Founders and operators who want trustless execution  
- Builders who want programmable business logic  
- Investors who need proof of coordination  
- Protocols who want to embed strategic triggers in real systems

---

For further questions, reach out via [Telegram](https://t.me/levaprotocol) or explore the [repo](https://github.com/leva-token-assets/leva).
