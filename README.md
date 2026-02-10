# AI-Generated Code Failure Rules

This repository defines a canonical set of failure modes and detection rules
**specific to AI-generated software**.

These rules target risks that are systematically missed by traditional
SAST, DAST, and coverage-based testing approaches, particularly in code
written or heavily assisted by large language models.

## Why this exists

AI-generated code often:
- Appears correct but violates intent
- Includes safety checks that do not actually protect anything
- Blurs trust boundaries
- Assumes execution order and hidden state
- Creates false confidence through superficial tests

This project formalizes those failure modes and provides machine-detectable
rules to surface them early.

## Framework

The rules are organized around five AI-specific failure categories:

1. Semantic Drift
2. Hallucinated Safety
3. Boundary Collapse
4. Temporal Coupling
5. False Confidence

These categories are defined in `framework/` and implemented as rule sets
under `rules/`.

## Tooling

Rules in this repository are currently implemented using Semgrep-compatible
patterns, but the framework itself is tool-agnostic.

## Status

This is the initial public release of the framework.

## Community Contributions

This project is intentionally open.

If you have observed failure modes that occur disproportionately
in AI-generated or AI-assisted code, we welcome contributions in
the form of rules, examples, or documentation.

Please read `CONTRIBUTING.md` before submitting a pull request to
ensure alignment with the framework.
