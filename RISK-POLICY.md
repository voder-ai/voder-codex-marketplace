# Voder Codex Marketplace Risk Management Policy

**Last reviewed:** 2026-08-25

This policy follows ISO 31000 and governs the public marketplace that connects
Codex clients to Voder's existing MCP service.

## Business Context

Codex desktop and CLI users install the Voder Early Access plugin to access
Voder accounting tools through the existing Voder MCP endpoint. Maintainers
publish and update the marketplace metadata. Failure can prevent installation,
misstate capabilities, direct users to the wrong endpoint or disclose
confidential information. This repository does not host the MCP service or
customer data.

## Confidential Information

This repository is public. Do not commit credentials, tokens, customer or tenant
identifiers, financial data, private provider identifiers, traffic or revenue
metrics, customer counts, pricing not already intentionally public or private
communications. Use generic descriptions. Any suspected secret exposure
requires immediate removal and rotation.

## Risk Appetite

**Risk appetite - Threshold: 5** of 25. Actions with cumulative residual risk
above 5 must be remediated or halted. This inherits Voder's founder-ratified
production appetite.

## Impact Levels

| Level | Label | Consequence |
|---|---|---|
| 1 | Negligible | No effect on Voder marketplace installation, OAuth authentication or MCP access. |
| 2 | Minor | Local contributor workflow is inconvenienced; Voder marketplace installation and published metadata remain correct. |
| 3 | Moderate | Marketplace publishing or updates are delayed, or confidential business information is committed and requires remediation without affecting Voder OAuth or the MCP endpoint. |
| 4 | Significant | Users cannot install the Voder Early Access plugin, cannot complete Voder OAuth authentication, are directed to the wrong MCP endpoint or receive materially misleading capability or policy information. |
| 5 | Severe | Credentials or customer financial data are exposed, the Voder Early Access plugin redirects users to a hostile endpoint, or trust and data security are materially compromised. |

## Likelihood Levels

| Level | Label | Description |
|---|---|---|
| 1 | Rare | Requires unusual conditions; exercised automated or architectural controls make occurrence very unlikely. |
| 2 | Unlikely | Could occur, but validation and review significantly reduce probability. |
| 3 | Possible | Could occur under normal conditions because coverage or controls are limited. |
| 4 | Likely | Expected without intervention because complexity or control gaps are high. |
| 5 | Almost certain | A known or observed gap exists with no effective control. |

## Risk Matrix

| Impact / Likelihood | 1 | 2 | 3 | 4 | 5 |
|---|---:|---:|---:|---:|---:|
| 1 Negligible | 1 | 2 | 3 | 4 | 5 |
| 2 Minor | 2 | 4 | 6 | 8 | 10 |
| 3 Moderate | 3 | 6 | 9 | 12 | 15 |
| 4 Significant | 4 | 8 | 12 | 16 | 20 |
| 5 Severe | 5 | 10 | 15 | 20 | 25 |

| Score | Label |
|---|---|
| 1-2 | Very Low |
| 3-5 | Low |
| 6-9 | Medium |
| 10-16 | High |
| 17-25 | Very High |

## Authorized Bypass Scenarios

- Risk-reducing or risk-neutral changes may proceed through the scorer's
  TTL-bounded `RISK_BYPASS: reducing` path after drift revalidation.
- Incident response is not a separate carve-out. It proceeds only when it
  reduces risk against the live incident baseline; an `incident-release` marker
  may only support that net-reducing restoration when CI is red or unreadable.
- Above-appetite risk cannot be bypassed by a prompt, environment variable or
  fabricated marker. Remediate to within appetite or halt.
- Older policies silent on this section permit only the risk-reducing and
  incident paths above until reviewed.

The pipeline risk scorer and problem-management process use this policy. Review
it after any security incident, material distribution change or at least every
three months.
