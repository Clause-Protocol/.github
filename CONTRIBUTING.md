# Contributing to Clause Protocol

Thank you for contributing to **Clause Protocol** — *"From Agent to Agent. From You to You."*

We welcome contributions from smart contract auditors, AI agent builders, and Model Context Protocol (MCP) developers.

---

## Core Protocol Invariants (Do Not Break)

Any change to smart contracts or MCP tooling must preserve the following invariants:
1. **Compiler Determinism:** Solidity `0.8.26`, `optimizer.enabled = false`, `runs = 200`, `evmVersion = "cancun"`.
2. **Immutable Supply & Quota:** `MAX_SUPPLY == 7777` and `MAX_PER_WALLET == 2` (lifetime primary mints).
3. **100% On-Chain Metadata:** `ClauseGenesis.tokenURI(tokenId)` and `tierOf(tokenId)` must resolve directly from on-chain `_tierWords` storage without external JSON dependencies.
4. **Zero Admin Over Assets:** No `Ownable`, no proxy pattern, and no `payable` functions in the core Genesis suite.
5. **English-Only Codebase:** All code comments, console logs, error messages, and documentation must be written concisely in English.

---

## Development Workflow

```bash
# 1. Install dependencies
npm install

# 2. Compile contracts
npm run compile

# 3. Test autonomous MCP puzzle + EIP-712 ticket flow
npm run test:mcp

# 4. Run local MCP & REST server (Port 3000)
npm run mcp:server
```

---

## Submitting a Pull Request

1. Fork the repository and create a feature or fix branch.
2. Ensure `npm run compile` finishes with zero warnings and `npm run test:mcp` passes cleanly.
3. Keep code comments minimal and exclusively in English.
4. Open a Pull Request completing all sections of the PR template.

