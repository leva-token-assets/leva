# LEVA Protocol Glossary

This glossary defines key terms used throughout the LEVA Protocol, agent registry, and burn-to-execution infrastructure. All terminology is schema-bound, execution-centric, and oriented toward verifiability.

---

## 🔁 Execution Flow Terms

**Burn**  
The irreversible act of destroying a LEVA token to initiate execution. Burns are final, non-recoverable, and cryptographically recorded on-chain. Each burn must include an `agent_id` reference and matches a versioned schema.

**Execution**  
The complete logic path initiated by a burn. It involves triggering a registered agent, validating input against a schema, running the logic path, and producing a structured output. Execution is deterministic and verifiable.

**Trigger**  
A synonym for initiating execution via burn. The trigger links the burn transaction to an agent and schema version, beginning the coordination process.

**Agent**  
A logic-bound execution unit registered in the protocol. Agents are version-controlled and schema-tied. Each agent has a unique ID and performs a specific strategic or operational function (e.g. pricing, GTM, investor memo).

**Schema**  
A JSON-based structure that defines valid input and output fields for a given agent. Schemas enforce determinism, prevent ambiguity, and allow outputs to be programmatically verified. All inputs must pass schema validation before execution.

**Output**  
The structured result of an agent's execution. Output must be JSON-formatted, match the schema, and include metadata (agent ID, version, timestamp, output hash, burn reference). Outputs may be delivered via webhook, IPFS, or other programmable dispatch methods.

---

## 🔍 Registry + Infrastructure Terms

**Agent Registry**  
The public list of all approved agents. Each entry includes agent ID, schema reference, version, description, and execution metadata. The registry is version-controlled and transparent.

**Burn Registry**  
The on-chain/off-chain hybrid record of all burns, linked to the agent triggered and the output returned. It is used for traceability, audit, and public verification. Outputs are referenced via hash and often pinned to IPFS.

**Schema Versioning**  
A strict semantic versioning system (e.g. `1.0.0`, `1.1.0`, `2.0.0`) used to track changes in schema logic. No schema may be modified retroactively. All changes require a new version and optional new agent mapping.

**Agent ID**  
A unique string identifying a registered agent. Format: `LEVA-<DOMAIN>-<NN>` (e.g. `LEVA-GTM-01`, `LEVA-INVEST-02`). Used in burn transactions to specify execution logic.

**Schema File**  
A `.json` file that defines the structure of expected inputs and outputs. Used to validate requests before execution and to interpret agent results. Stored in `/schemas/` and publicly referenced in the agent registry.

**Output Hash**  
A SHA-256 or Keccak256 hash of the agent output used for verification. Paired with a timestamp and burn transaction reference to guarantee integrity. Stored in the burn registry.

**IPFS Reference**  
Optional but encouraged. Stores the raw output in a decentralized file system (IPFS) with its CID linked to the output hash and burn tx. Ensures off-chain storage integrity.

**Webhook**  
A dispatch method that delivers execution results (output payload) to a user-defined endpoint. Common for dev teams integrating LEVA into internal tools.

**Validator**  
(Upcoming role) Validators will check that agent outputs match schema logic, that no tampering has occurred, and that agent behavior adheres to expected norms. Validators may eventually form part of a performance mesh.

---

## 🧠 Agent Logic Terms

**Schema-Bound**  
All agents must bind to a specific schema version. This ensures that execution inputs are validated, and that logic is repeatable and predictable.

**Version-Controlled Agent**  
Agents are locked to a specific version. If logic changes, a new version must be created. This preserves determinism and auditability.

**Composable Execution**  
LEVA execution can be composed into broader workflows — called by other systems, used in apps, or triggered by bots — without breaking schema integrity.

**Model-Agnostic**  
Agents are not hardwired to OpenAI, Anthropic, or any single model. Execution is schema-bound, meaning it can be handled by any engine that adheres to the schema and returns structured outputs.

**Deterministic Output**  
Outputs must be reproducible for the same inputs. Non-deterministic prompts or generative randomness is not allowed in agent logic.

**Routing Logic**  
The logic used to select the execution path once an agent is triggered — including branching conditions, schema mapping, and post-processing rules. Currently internal to the agent.

---

## 🛠 File + Repo Structure

**`/agents/`**  
Contains metadata for each registered agent, including descriptions, logic overview, schema link, and ID.

**`/schemas/`**  
Contains all valid JSON schemas, versioned and used in execution validation.

**`/burn-registry/`**  
Stores output logs, burn transaction hashes, IPFS CIDs, and sample outputs.

**`/docs/`**  
Contributor-facing documentation including guides, logic flow, and submission protocols.

**`/output-examples/`**  
Optional directory for storing example outputs for each agent/schema pair.

---

LEVA defines strategy execution as a deterministic protocol — not a product. This glossary ensures consistent vocabulary across code, documentation, and coordination logic.
