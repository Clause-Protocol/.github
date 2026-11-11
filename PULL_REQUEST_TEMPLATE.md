## Summary

Describe the purpose of this Pull Request and the components touched (`contracts/`, `mcp-server/`, `scripts/`, or `docs/`).

---

## Protocol Invariant Checklist

- [ ] **Compiler Settings Unchanged:** Compiles cleanly with Solidity `0.8.26` (`optimizer: false`, `evmVersion: "cancun"`).
- [ ] **Core Invariants Intact:** Does not alter `MAX_SUPPLY (7777)`, `MAX_PER_WALLET (2)`, or on-chain `_tierWords` provenance verification.
- [ ] **MCP Flow Verified:** `npm run test:mcp` passes end-to-end.
- [ ] **Code Hygiene:** Minimal comments, zero unused files/dependencies, and 100% English logs/documentation.

