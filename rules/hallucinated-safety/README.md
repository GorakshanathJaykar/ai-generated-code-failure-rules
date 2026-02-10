# Hallucinated Safety

Hallucinated safety occurs when code contains constructs that *appear* to
enforce correctness, robustness, or security but do not actually alter
execution in a meaningful way.

These patterns create a **false sense of safety**: the code looks defensive
in reviews and often passes tests, yet unsafe states are still allowed to
propagate.

This failure mode is disproportionately common in **AI-generated or
AI-assisted code**, where models optimize for perceived best practices
(e.g., “add validation”, “add error handling”) without enforcing the
corresponding control-flow guarantees.

Rules in this category detect safety constructs that fail to **stop,
redirect, or constrain execution**.

## HS-001 — Guard Clause Without Enforcement

Detects guard clauses that acknowledge an invalid or unsafe condition but
do not prevent subsequent execution.
The guard condition is evaluated, but its result is effectively ignored.
This pattern gives reviewers the impression that invalid states are handled,
while sensitive operations still execute unconditionally.

AI-generated code frequently produces this pattern because it adds checks
to satisfy surface-level correctness rather than enforcing failure semantics.

## HS-002 — Swallowed Exceptions

Catching exceptions without enforcing failure semantics is a common
AI-generated anti-pattern. Logging or commenting on errors without
altering control flow leads to silent corruption and unsafe continuation.

This rule flags catch blocks that do not throw, return, or otherwise
terminate execution.
