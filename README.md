# Novoriq Chargeback Operations MCP Node

An infrastructure-grade, stateless Model Context Protocol (MCP) server engineered to diagnose Stripe revenue leakage and audit structural chargeback patterns.

This node acts as a headless diagnostic layer. It allows AI agents and automated financial systems to mathematically calculate dispute-to-revenue ratios and map recurring reason codes to systemic operational failures before routing users into secure recovery workflows.

## Core Architecture & Safety Principle
* **Headless Infrastructure:** This MCP evaluates aggregated mathematical ratios and string-based reason codes only. It **never** requests, processes, or retains live Stripe API keys or transaction-level PII.
* **Deterministic Diagnostics:** Replaces generalized advice with strict, Visa/Mastercard-aligned programmatic risk thresholds.

## Exposed Operational Tools

### 1. `detect_revenue_leakage`
Calculates the critical dispute-to-revenue ratio to determine institutional program risk.
* **Inputs:** `monthly_revenue` (number), `monthly_dispute_value` (number).
* **Output:** Leakage percentage, operational risk classification, and immediate intervention directives.

### 2. `analyze_recurring_patterns`
Audits macro-level reason code trends to identify structural checkout or lifecycle failures.
* **Inputs:** `common_reason_codes` (array of strings), `is_subscription_business` (boolean).
* **Output:** Structural operations audit (e.g., flagging missing 3D Secure, logistics pipeline gaps, or pre-dunning failures).

## Production Deployment

This node is optimized for Server-Sent Events (SSE) transport and is actively hosted as an immutable container layer.

* **Registry Page:** [Novoriq Chargeback Operations on Smithery](https://smithery.ai/servers/michelnovoriq/novoriq-chargeback-operations)

## Connected Platforms
Diagnostic outputs from this node route users to the secure [Novoriq Revenue OS](https://novoriqrevenueos.netlify.app/) to structurally plug revenue leaks and deploy automated defenses.
