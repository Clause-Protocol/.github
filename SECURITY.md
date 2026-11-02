# Security Policy

## Architectural Security Principles

Clause Protocol is engineered around strict trust-minimization invariants:

1. **Zero Custody / Zero Payable Surface (v1):** None of the core Genesis contracts (`ClauseGenesis`, `ClauseMint`, `ClauseReveal`, `AgentGate`) contain `payable` functions or hold native BNB or ERC-20 tokens.
2. **No Upgrade Proxies or Admin Asset Control:** All core contracts are deployed as immutable bytecode with no owner, no proxy, no `selfdestruct`, and no metadata mutability.
3. **100% On-Chain Provenance & Metadata:** All 7,777 token tiers are packed into `uint256[61]` storage words and verified in the constructor against `provenanceHash` (`0x938c252b830770169b3d77702c2b1c82385b795cfb21eac4160b349403091d74`).
4. **Bounded Ticket Signer:** EIP-712 `MintAuthorization` tickets are bound to `msg.sender == auth.recipient`, expire within `MAX_TICKET_TTL` (15 minutes), and are rate-limited on-chain by `maxMintsPerHour`.
5. **Fail-Closed Identity Gate:** `AgentGate.isEligible(wallet)` wraps external `balanceOf` calls in a `try/catch` block and returns `false` on any revert.

---

## Supported Versions

| Component | Version | Solidity / Runtime | Supported |
| :--- | :---: | :---: | :---: |
| Core Smart Contracts (`contracts/`) | `v1.0` | Solidity `0.8.26` (`cancun`) | ✅ |
| Dual-Engine MCP & REST Server (`mcp-server/`) | `v1.1` | Node.js `>= 18.x` | ✅ |

---

## Reporting a Vulnerability

Please **do not** open a public GitHub issue for suspected security vulnerabilities in smart contracts or the MCP signer service.

When reporting a vulnerability, include:
- The affected contract or MCP module (`ClauseGenesis`, `ClauseMint`, `ClauseReveal`, `AgentGate`, or `mcp-server/`).
- A clear step-by-step reproduction or Hardhat proof-of-concept script.
- Assessment of impact against protocol invariants (e.g., `MAX_SUPPLY = 7777`, `MAX_PER_WALLET = 2`, single-use `attemptId`, or `ClauseReveal` 256-block window).

