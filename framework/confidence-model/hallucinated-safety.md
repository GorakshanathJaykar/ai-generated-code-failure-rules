# Confidence Penalty Model — Hallucinated Safety

## Scope

This document defines how violations in the Hallucinated Safety (HS)
category impact overall release confidence.

HS violations represent trust failures where code appears defensive
but does not enforce failure semantics.

---

## Severity Tiers

| Tier | Description |
|------|-------------|
| HS-Critical | Safety construct is entirely ineffective in a critical path |
| HS-High | Safety construct exists but does not enforce control flow |
| HS-Medium | Partial enforcement with unsafe fallback |
| HS-Low | Cosmetic safety with limited impact |

---

## Base Penalties

| Severity | Penalty |
|---------|---------|
| HS-Critical | −20 |
| HS-High | −12 |
| HS-Medium | −6 |
| HS-Low | −2 |

---

## Context Multipliers

### Execution Criticality

| Context | Multiplier |
|--------|------------|
| Auth / Payments / Persistence | ×1.5 |
| External boundary | ×1.3 |
| Internal logic | ×1.0 |
| Non-critical path | ×0.7 |

### Failure Propagation

| Behavior | Multiplier |
|---------|------------|
| Error swallowed after state mutation | ×1.5 |
| Error swallowed, state unclear | ×1.3 |
| Error logged only | ×1.1 |

---

## Confidence Caps

| Condition | Max Confidence |
|----------|----------------|
| Any HS-Critical | ≤70 |
| ≥2 HS-High | ≤75 |
| HS in auth/payment | ≤65 |
| HS in error-handling layer | ≤60 |

---

## Interpretation

Hallucinated Safety violations directly undermine trust in the system.
Confidence should be capped until these violations are resolved,
regardless of test coverage or other metrics.