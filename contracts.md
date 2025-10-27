# Contracts

**Last updated:** 2025-10-27

Contents
- Token
- DEX Contracts
- esALB Contracts
- Verification & Security
- Changelog
- Contact / Disclaimer

---

## Summary
This document lists primary contracts and recommended verification steps for the project on Base (basescan.org). All links point to BaseScan; verify contract source and ownership before interacting.

---

## Token
- Ticker: ALB
- Contract: https://basescan.org/token/0x1dd2d631c92b1acdfcdd51a0f7145a50130050c4
- Max supply: 510,000,000
- Initial circulating supply: 5.1% (26,000,000)
- Suggested checks:
  - Confirm "Contract Verified" on BaseScan.
  - Retrieve ABI from the verified source.
  - Confirm owner/multisig and timelock status.

---

## DEX Contracts

- Factory: https://basescan.org/address/0x3e84d913803b02a4a7f027165e8ca42c14c0fde7
- Router: https://basescan.org/address/0x8c1A3cF8f83074169FE5D7aD50B978e1cD6b37c7
- Farm contract: https://basescan.org/address/0x52eaecac2402633d98b95213d0b473e069d86590
  - Controller (selective timelock proxy): https://basescan.org/address/0x16f1F80654F2FEA97293321675907CFA2e23e4fB
  - Notes:
    - Privileged operations (change owner, modify ALB emission rate, etc.) are protected by timelock.
    - Adding farms or changing non-privileged parameters can be performed without timelock for speed.
    - Current deposit fee: 0% — reported as immutable post-launch (verify in code).
- Area 51 Router: https://basescan.org/address/0x3485F8E155973cC247CBEa9E77C0dBBB4BBb79E7
- Area 51 Factory: https://basescan.org/address/0x2d5dd5fa7B8a1BFBDbB0916B42280208Ee6DE51e

---

## esALB Contracts

- esALB Token: https://basescan.org/address/0xe1afc637f41e05efe08d55296a2ccff0072a4587
- config.esMasterAddress: https://basescan.org/address/0xd3968a4a07d64c6e16982d45191b9a09a261ec88
- esALB-ETH pair: https://basescan.org/address/0x176ca19007b1e2c9d85b8ecd68f89bb7f8a208f0

---

## Verification & Security Checklist
For each contract:
1. Confirm "Contract Verified" status on BaseScan.
2. Download and inspect ABI and source code.
3. Identify owner addresses, multisig or Gnosis Safe, and timelock contracts.
4. Search for admin/privileged functions and confirm timelock coverage.
5. Check for immutable flags (e.g., deposit fee immutability).
6. Look for published audit reports; if none, consider requesting an audit.

Recommended additions to this doc:
- Owner / multisig addresses and links.
- Audit report links and summary.
- ABI links (or embedded ABI files).
- Short changelog entry for any address changes or upgrades.

---

## Example: quick BaseScan verification script (optional)
A simple curl + jq example to fetch contract page metadata (adjust as needed for BaseScan API or HTML parsing):

```bash
# filepath: scripts/check_basescan.sh
#!/usr/bin/env bash
set -euo pipefail
if [ -z "${1-}" ]; then
  echo "Usage: $0 <contract-address>"
  exit 2
fi
addr="$1"
# Note: this parses the contract page HTML; consider using BaseScan API if available.
curl -s "https://basescan.org/address/${addr}" | grep -i "Contract Source" -A2 || echo "Unable to detect verification from HTML; use BaseScan API or manual check."
```

---

## Changelog
- 2025-10-27 — Converted document to English; added verification checklist and script example.

---

## Contact / Disclaimer
This document is for informational purposes only and is not investment advice. Always perform your own due diligence before interacting with contracts.
