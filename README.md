# SPL: Semantic Pattern Language (v2.3)

The minimal, verifiable language to compose intelligent systems from patterns.

[License: Apache-2.0](LICENSE) • [Version](VERSION)

## What is SPL (in one screen)

SPL is the pattern language for quantum AI, it is the first AI language.

- Verifiable: every execution returns structured output plus a truth score
- Composable: patterns declare contracts and dependencies and can be safely combined
- Layered: from L0 meta-structure to L1 critical building blocks up to complete solutions
- Reality-agnostic: digital, physical, and hybrid systems share the same contracts

That’s it. SPL is a small set of rules that makes AI systems predictable, auditable, and reusable.

## The Three Structures (the heart of SPL)

Every SPL pattern has exactly three structural sections. These map intelligence, execution, and ethics into one contract.

```
contract:     # Intelligence (LLM Layer)
  goal:        # What to achieve
  return:      # Exact output structure
  warnings:    # Guardrails and constraints
  context:     # Background and assumptions

execution:    # Runtime (Loop / Inspect)
  steps:       # Iterations and checks
  monitors:    # Self-inspection signals

guarantees:   # Culture (Ethics & Compliance)
  success_criteria:  # What ‘good’ means
  metrics:           # How we measure it
  compliance:        # Laws/policies to honor
```

- Intelligence (contract): Greg’s 4 pillars — Goal, Return Format, Warnings, Context
- Runtime (execution): Print AI maxims — Loop, Inspect, and Print
- Culture (guarantees): Human alignment — success, metrics, compliance, safety

These three structures are defined once at L0 (meta-pattern) and inherited everywhere.

## Why “Quantum”-inspired (without quantum hardware)

SPL borrows quantum ideas to describe composition behavior using classical computation:

- Superposition: multiple candidate patterns can coexist for a goal
- Contextual collapse: runtime selects the best pattern (or weighted ensemble) for the current context
- Entanglement: shared signals/constraints couple patterns so changes in one update truth/risks in others
- Interference: scoring and validation amplify or suppress contributions during composition

All of this is implemented with probabilities, scores, and dependency graphs — no quantum computers required. The result is adaptive behavior with measurable confidence.

## Why SPL is an AGI architecture

- Cognitive patterns (L2) define general capabilities: value-system, knowledge-representation, experience-acquisition, motivation, expectation, ethical-reasoning
- Cross-reality contracts let the same intelligence act in digital, physical, and hybrid environments
- The three structures guarantee alignment and verifiability at every step
- Generalization comes from composition, not model retraining

SPL is how you specify, measure, and align intelligence universally.

## What's in this repository

**Foundational Patterns (v2.3):**
- **L0 Meta-Pattern**: The foundation all patterns inherit from (`patterns/meta-pattern/v2.3/meta-pattern.yaml`)
- **L1 Critical Patterns**: 13 universal building blocks (`patterns/critical-patterns/*/v2.3/*.yaml`)
- **L1C Cognitive Patterns**: 6 AGI-enabling patterns (`patterns/cognitive-patterns/*/v2.3/*.yaml`)
- **Pattern Registry**: Unified index of all patterns (`patterns/pattern-index-v2.3.yaml`)

**Documentation:**
- [What is SPL?](doc/what-is-spl.md) - Start here
- [Critical Patterns Guide](doc/patterns/what-are-l1-critical-patterns.md)
- [Cognitive Patterns Guide](doc/patterns/what-are-l1c-cognitive-patterns.md)
- [Six Layers Overview](doc/patterns/spl-six-layers-overview.md)
- [Versioning Policy](doc/SPL_VERSIONING_POLICY.md)

**Total**: 20 foundational patterns that compose infinitely

## Muscle, Structure, Culture

- Muscle (compute): model capability and raw power
- Structure (SPL): meta-pattern, layers, and the three structures that make behavior predictable
- Culture (ethics): guarantees that encode values and compliance

Pillars mapping:
- Greg’s 4 (Intelligence): Goal, Return Format, Warnings, Context
- Print AI (Runtime): Loop and Inspect (Print via return)
- Asimov-style (Culture): Human protection, human direction, system preservation (expressed via guarantees)

## Minimal example (10 lines)

```yaml
id: "validator/email:v1.0"
layer: "L1"
contract: { goal: "validate an email", return: { is_valid: bool }, warnings: [], context: {} }
execution: { steps: [check_rfc5322, check_dns_mx], monitors: [timeouts, retries] }
guarantees: { success_criteria: ["truth_score>0.95"], metrics: ["latency_ms"], compliance: {} }
```

For deeper material, see the docs linked above. Build patterns. Compose them. Measure truth. That’s SPL.
