# LEVA Protocol

**LEVA is an execution-layer protocol.**  
Every LEVA token burned is an irreversible act of coordination. Each burn references a registered agent and triggers verifiable logic — producing a timestamped output and permanently reducing supply.

No staking. No passive emissions. Only provable execution.

---

## ⚙️ How It Works

1. **Burn:** A user burns LEVA tokens.  
2. **Reference:** The burn includes an `agent_id` and points to a public `schema`.  
3. **Execute:** The registered agent runs logic tied to that schema.  
4. **Output:** The result is versioned, timestamped, and publicly linked.  
5. **Verify:** Anyone can check the burn, agent, and output on-chain.

---

## ✅ Example Flow

- **Burn Transaction:** `0xABCDEF1234567890...`  
- **Agent ID:** `AGENT-001`  
- **Schema:** `/registry/agent-001.json`  
- **Output:** `https://leva.io/output/AGENT-001/tx/0xABCDEF1234567890`

---

## 📂 Registry Example

```json
{
  "agent_id": "AGENT-001",
  "schema_ref": "https://leva.io/registry/agent-001.json",
  "status": "active"
}
