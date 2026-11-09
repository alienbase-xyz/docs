# Security Policy

## Reporting a Vulnerability

The Alien Base team takes security seriously. We appreciate your efforts to responsibly disclose your findings and will make every effort to acknowledge your contributions.

### How to Report a Security Vulnerability

**Please do NOT report security vulnerabilities through public GitHub issues.**

Instead, please report them via one of the following methods:

1. **Email:** security@alienbase.xyz
2. **Discord:** Direct message to `@security-team` in the [Alien Base Discord](https://discord.gg/alienbase)
3. **Bug Bounty Platform:** [Immunefi](https://immunefi.com/) (if applicable)

### What to Include in Your Report

To help us better understand and resolve the issue, please include as much of the following information as possible:

- **Type of vulnerability** (e.g., smart contract bug, documentation error leading to security risk)
- **Full description** of the vulnerability
- **Step-by-step instructions** to reproduce the issue
- **Potential impact** of the vulnerability
- **Suggested fix** (if you have one)
- **Your contact information** for follow-up questions

### Example Report Format

```
Subject: [SECURITY] Brief description of vulnerability

Vulnerability Type: Smart Contract / Documentation / Other

Description:
[Detailed description of the vulnerability]

Steps to Reproduce:
1. [First step]
2. [Second step]
3. [etc.]

Impact:
[What could an attacker do with this vulnerability?]

Suggested Fix:
[If you have suggestions]

Contact:
[Your preferred contact method]
```

## Response Timeline

We are committed to responding to security reports in a timely manner:

- **Initial Response:** Within 48 hours of receiving your report
- **Status Update:** Within 7 days with our assessment and planned actions
- **Resolution:** Varies based on severity and complexity
  - Critical: 1-7 days
  - High: 7-30 days
  - Medium: 30-90 days
  - Low: 90+ days or next scheduled release

## Disclosure Policy

### Coordinated Disclosure

We follow a coordinated disclosure process:

1. **You report** the vulnerability privately
2. **We acknowledge** receipt and begin investigation
3. **We develop** and test a fix
4. **We deploy** the fix to production
5. **We publicly disclose** the vulnerability (with your permission)
6. **You receive** recognition and rewards (if applicable)

### Public Disclosure Timeline

- We will work with you to determine an appropriate disclosure timeline
- Typical timeline: 90 days from initial report
- Critical vulnerabilities may be disclosed sooner after fixes are deployed
- We will credit you in the disclosure (unless you prefer to remain anonymous)

## Supported Versions

We provide security updates for the following:

| Component | Version | Supported |
|-----------|---------|-----------|
| Documentation | Latest | [YES] |
| Smart Contracts | V2 | [YES] |
| Smart Contracts | V3 | [YES] |
| esALB Contracts | Current | [YES] |
| Legacy Contracts | V1 | [WARNING] Limited |

[WARNING] Limited support means we will assess severity but may not provide updates.

## Security Best Practices for Users

### Wallet Security

**Protect Your Private Keys:**
- Never share your private keys or seed phrase
- Use hardware wallets for large amounts
- Enable 2FA where possible
- Use strong, unique passwords

**Verify Contracts:**
- Always verify contract addresses on [BaseScan](https://basescan.org)
- Bookmark official links
- Be wary of phishing attempts
- Double-check URLs before connecting wallet

### Transaction Safety

**Before Signing:**
- Review transaction details carefully
- Verify the contract address
- Check the token amounts
- Understand what you're approving
- Use simulation tools when available

**Token Approvals:**
- Only approve what you need
- Revoke unused approvals regularly
- Use tools like [Revoke.cash](https://revoke.cash)
- Monitor your allowances

### Phishing Prevention

**Red Flags:**
- Unsolicited DMs offering support
- Urgent requests for action
- Requests for private keys or seed phrases
- Suspicious links or attachments
- Too-good-to-be-true offers

**Verify Official Channels:**
- Website: https://alienbase.xyz
- Twitter: [@AlienBase_xyz](https://twitter.com/AlienBase_xyz)
- Discord: [Official Invite Link](https://discord.gg/alienbase)
- GitHub: [github.com/alienbase-xyz](https://github.com/alienbase-xyz)

## Smart Contract Security

### Audits

Our smart contracts have been audited by reputable security firms:

- **V2 Contracts:** [Audit Report Link]
- **V3 Contracts:** Based on audited Uniswap V3 and Bunni
- **esALB Contracts:** [Audit Report Link]

**Note:** Audits do not guarantee security. Always do your own research and only invest what you can afford to lose.

### Known Risks

**Smart Contract Risks:**
- Smart contracts are immutable once deployed
- Bugs may exist despite audits
- Upgradeable contracts have admin keys
- Oracle dependencies may fail

**Market Risks:**
- Impermanent loss in liquidity pools
- Price volatility
- Slippage on large trades
- Front-running and MEV

**Operational Risks:**
- Network congestion
- RPC failures
- UI bugs
- Third-party integrations

### Emergency Procedures

**If You Suspect a Security Issue:**

1. **Stop Interacting** with the affected contract
2. **Document** what you observed
3. **Report** to security@alienbase.xyz immediately
4. **Monitor** official channels for updates
5. **Follow** team instructions

**Emergency Contacts:**
- Security Email: security@alienbase.xyz
- Discord: @security-team
- Twitter: [@AlienBase_xyz](https://twitter.com/AlienBase_xyz)

## Bug Bounty Program

We value the security research community and offer rewards for valid vulnerability reports.

### Scope

**In Scope:**
- Smart contracts deployed on Base mainnet
- Official frontend applications
- API endpoints
- Documentation leading to security risks

**Out of Scope:**
- Third-party integrations
- Known issues already reported
- Theoretical vulnerabilities without proof of concept
- Social engineering attacks
- Physical attacks

### Rewards

Rewards are based on severity and impact:

| Severity | Smart Contract | Other |
|----------|----------------|-------|
| Critical | Up to $50,000 | Up to $5,000 |
| High | Up to $25,000 | Up to $2,500 |
| Medium | Up to $10,000 | Up to $1,000 |
| Low | Up to $1,000 | Up to $500 |

**Factors Affecting Rewards:**
- Severity and impact
- Quality of report
- Proof of concept
- Suggested fix
- Responsible disclosure

### Eligibility

To be eligible for rewards:
- Follow responsible disclosure
- Provide detailed report
- Don't exploit the vulnerability
- Don't disclose publicly before fix
- Comply with all laws
- Be first to report the issue

## Security Updates

### How We Communicate Security Issues

**Channels:**
- Security advisories on GitHub
- Announcements in Discord
- Twitter updates
- Email to affected users (if applicable)

**What We Disclose:**
- Nature of the vulnerability
- Affected versions/contracts
- Remediation steps
- Credit to reporter (with permission)

### Staying Informed

**Subscribe to Updates:**
- Watch this repository on GitHub
- Join [Discord](https://discord.gg/alienbase)
- Follow [@AlienBase_xyz](https://twitter.com/AlienBase_xyz)
- Enable GitHub security alerts

## Documentation Security

### Reporting Documentation Issues

Documentation errors can lead to security risks. Please report:

- Incorrect contract addresses
- Outdated security information
- Misleading instructions
- Broken links to security resources
- Missing warnings or disclaimers

**Report via:**
- GitHub Issues (for non-sensitive issues)
- security@alienbase.xyz (for sensitive issues)

### Documentation Review Process

All documentation changes undergo:
- Technical accuracy review
- Security implications assessment
- Link validation
- Community feedback period

## Contact

**Security Team:**
- Email: security@alienbase.xyz
- Discord: @security-team
- PGP Key: [Link to public key]

**General Inquiries:**
- Website: https://alienbase.xyz
- Twitter: [@AlienBase_xyz](https://twitter.com/AlienBase_xyz)
- Discord: [discord.gg/alienbase](https://discord.gg/alienbase)

## Acknowledgments

We thank the following security researchers for responsibly disclosing vulnerabilities:

- [Researcher Name] - [Brief description] - [Date]
- [To be updated as reports are received]

---

**Last Updated:** 2026-01-07  
**Version:** 1.0

Thank you for helping keep Alien Base and our community safe!
