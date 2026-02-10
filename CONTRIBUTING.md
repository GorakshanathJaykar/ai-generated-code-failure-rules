# Contributing to AI-Generated Code Failure Rules

Thank you for your interest in contributing.

This project defines a canonical framework for identifying and scoring
failure modes that occur disproportionately in AI-generated or
AI-assisted code.

Contributions are welcome — but must align with the framework’s
principles and taxonomy.

---

## What We Are Looking For

We welcome contributions that add:

- New detection rules for existing failure categories
- Concrete examples of AI-generated code failures
- Additional languages for existing rules
- Documentation improvements that clarify failure modes

---

## What We Are NOT Looking For

To preserve coherence, we do not accept contributions that:

- Introduce generic style, lint, or formatting rules
- Reclassify traditional bugs without AI-specific rationale
- Add rules without a clear failure-mode explanation
- Change the core failure taxonomy without prior discussion

This is not a general-purpose SAST rule repository.

---

## Rule Contribution Requirements

Every new rule must include:

1. **Failure Category**
   - One of:
     - Semantic Drift
     - Hallucinated Safety
     - Boundary Collapse
     - Temporal Coupling
     - False Confidence

2. **Human Explanation**
   - Why this failure occurs in AI-generated code
   - Why traditional tools miss it

3. **Risk Rationale**
   - What assumptions are violated
   - How this impacts system trust

4. **Executable Rule**
   - Semgrep, CodeQL, or equivalent
   - Tool-agnostic logic preferred

5. **Examples**
   - Minimal failing example
   - Recommended fix

Pull requests missing these elements will not be accepted.

---

## Proposing New Failure Modes

If you believe a new failure category is needed:

1. Open a GitHub Discussion
2. Describe:
   - Why existing categories are insufficient
   - Evidence from AI-generated code
   - How the new category differs structurally

New categories are added conservatively.

---

## Review Philosophy

Rules are reviewed for:
- Conceptual correctness
- AI-specific relevance
- Consistency with the framework
- Signal-to-noise ratio

Not all contributions will be accepted.

Rejection does not imply lack of value — only misalignment.


## Attribution

All accepted contributors are credited in the repository.
The framework and taxonomy remain curated to ensure consistency.

By contributing, you agree to abide by this framework and its goals.
