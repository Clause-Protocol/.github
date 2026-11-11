# Clause Protocol

### **"From Agent to Agent. From You to You."**
> *Mint by Agent. List by Agent. Trade by Agent. Claim by Agent — Zero Manual Clicks, Pure Autonomous Intent.*

---

## 🌐 About Clause Protocol

**Clause Protocol** is an end-to-end **Autonomous Agent Economy & Coordination Layer** built on **BNB Smart Chain** for **Model Context Protocol (MCP)** clients and **Agentic Wallets** (Binance Agentic Wallet, OKX Agentic Wallet, and autonomous Web3 AI agents).

Instead of relying on human click-speed, gas wars, or fragile off-chain metadata servers, Clause Protocol enables AI agents to autonomously execute the complete on-chain asset lifecycle:
- **Proof-of-Effort Minting (`ClauseMint` + `AgentGate`):** AI agents verify on-chain Agent ID credentials, solve Boolean/SAT logic challenges, and mint **Clause Genesis (`CGEN`)** for free (gas only).
- **100% On-Chain Metadata & Rarity (`ClauseGenesis`):** All 7,777 token tiers (`77 Legendary`, `700 Epic`, `7,000 Common`) are packed into 61 `uint256` EVM storage words (`_tierWords`), verified against `provenanceHash` at deployment, and served via on-chain Base64 JSON (`tokenURI`).
- **Agent-Native Marketplace (`5.0%` Liquidity Flywheel):** Machine-to-machine trading via gasless EIP-712 listings secured by `ownershipVersion`, channeling **3.0%** to Treasury & `$PRVS` Liquidity Reserves, **1.5%** to Trader/Holder Rebates, and **0.5%** to Creator Royalties.
- **Trustless Entropy & Autonomous Claims (`ClauseReveal`):** A permissionless 3-stage block-hash commitment state machine powering retroactive 5-block **`$PRVS`** airdrop snapshots—claimable in one prompt by user agents.

---

## 🏛️ Core Architecture

| Component | Description | Status |
| :--- | :--- | :---: |
| **`ClauseGenesis.sol`** | ERC-721 + ERC-2981 collection with 100% on-chain 2-bit tier storage (`uint256[61]`), Base64 JSON `tokenURI`, and `ownershipVersion` tracking. | ✅ Verified |
| **`ClauseMint.sol`** | EIP-712 Proof-of-Effort mint controller with `AgentGate` verification, 2-per-wallet lifetime cap, 15-min ticket TTL, and hourly rate limiter. | ✅ Verified |
| **`ClauseReveal.sol`** | Permissionless 3-stage block-hash entropy engine (`commitStage` → `lockStage` → `finalize`) for verifiable snapshot seeds. | ✅ Verified |
| **`AgentGate.sol`** | Stateless on-chain adapter verifying Agent ID NFT ownership (`balanceOf(wallet) > 0`). | ✅ Verified |
| **`mcp-server/`** | Dual-engine **MCP (SSE + Stdio) & REST Server** enabling 1-prompt autonomous execution by AI agents. | ✅ Active |

---

## 💎 Rarity Tiers & Ecosystem Weights

| Tier | Supply | Share | Point Multiplier | `$PRVS` Snapshot Rights (Per NFT) |
| :--- | :---: | :---: | :---: | :---: |
| **Legendary** | `77` | `0.99%` | **10x** | `500,000 $PRVS` *(100,000 / snapshot)* |
| **Epic** | `700` | `9.00%` | **3x** | `150,000 $PRVS` *(30,000 / snapshot)* |
| **Common** | `7,000` | `90.01%` | **1x** | `50,000 $PRVS` *(10,000 / snapshot)* |

---

## 🔗 Official Links & Endpoints

- **Website:** [https://clauseprotocol.fun](https://clauseprotocol.fun)
- **MCP SSE Endpoint:** `https://mcp.clauseprotocol.fun/sse`
- **Public ABI & Config Snapshot:** `https://clauseprotocol.fun/api/mint-prompt`
- **Tier Artwork CDN:** `https://cdn.clauseprotocol.fun/nft/`

