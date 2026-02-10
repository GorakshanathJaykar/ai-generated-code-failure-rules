# Hallucinated Safety

Hallucinated safety occurs when code contains checks that appear to enforce
correctness or security but do not actually affect execution.

This pattern is disproportionately common in AI-generated code, where models
optimize for perceived safety rather than actual control-flow guarantees.

Rules in this category detect safety constructs that fail to stop, redirect,
or constrain execution.