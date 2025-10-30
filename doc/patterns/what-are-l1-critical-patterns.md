# What are Critical Patterns?

Version: 2.3  
Owner: SPLiQ team  
License: Apache 2.0  
Status: Public explainer (publishable)  
Audience: Developers, architects, and AI engineers understanding SPL's core capabilities

---

## Executive Summary

Critical Patterns are the foundational building blocks of SPL—13 universal patterns that define what intelligent systems **do**. They represent the core capabilities required across all systems, regardless of whether they operate in digital, physical, or hybrid realities.

---

## Definition

A **Critical Pattern** is a Layer 1 (L1) pattern that:

1. **Defines a fundamental capability** - Represents a core action or structure needed by intelligent systems
2. **Works everywhere** - Functions consistently across digital, physical, and hybrid realities
3. **Inherits from meta-pattern** - Directly implements the L0 meta-pattern specification
4. **Composes freely** - Combines with other patterns to create complex behaviors
5. **Has minimal overlap** - Represents a distinct architectural role

**Think of Critical Patterns as the "verbs" of SPL** - they define fundamental actions that can be composed to create sophisticated intelligent systems.

---

## The L1 Test: What Makes a Pattern "Critical"?

Not every pattern belongs at L1. A pattern qualifies as **Critical** only if it passes ALL these tests:

### 1. ✅ **Cannot be decomposed into simpler patterns**
   - The pattern represents an atomic, irreducible capability
   - It cannot be built by combining other L1 patterns
   - Example: `validator` cannot be reduced to simpler patterns
   - Counter-example: "authentication" = `validator` + `policy-guard` (composable, not L1)

### 2. ✅ **Is reality-agnostic**
   - Works in digital, physical, AND hybrid realities
   - The core capability doesn't depend on a specific reality
   - Example: `agent` works as web agent (digital), robot (physical), AR assistant (hybrid)
   - Counter-example: "web form" only makes sense in digital reality (not L1)

### 3. ✅ **Is technology-agnostic**
   - Doesn't require specific technologies, frameworks, or platforms
   - Can be implemented in any suitable technology
   - Example: `translator` works with any data formats/protocols
   - Counter-example: "Kubernetes deployment" requires K8s (not L1, it's L3)

### 4. ✅ **Represents WHAT, not HOW**
   - Defines a capability (what systems do), not an implementation (how to do it)
   - The pattern is about outcomes, not techniques
   - Example: `uncertainty-handler` defines what (manage uncertainty), not how (Bayesian vs fuzzy logic)
   - Counter-example: "caching" is a technique (how to optimize), not a capability (not L1)

### 5. ✅ **Is irreducible (minimum sufficient set)**
   - Removing this pattern would leave a gap in capabilities
   - Adding it doesn't duplicate existing patterns
   - The 13 Critical Patterns are the minimum set needed
   - Counter-example: "logging" = `monitor` + `documenter` (redundant, not L1)

---

## Why These 13 and Not Others?

### Patterns That Failed the L1 Test:

**Infrastructure patterns** (deployment, scaling, monitoring):
- ❌ Technology-specific (Docker vs K8s vs fleet management)
- ❌ Represent HOW to run systems, not WHAT they do
- ✅ Belong at L3 (technology patterns) or L5 (solutions)

**Security patterns** (authentication, encryption, audit):
- ❌ Decomposable: auth = `validator` + `policy-guard`
- ❌ Encryption is a technology choice (RSA vs AES vs quantum)
- ✅ Composable from existing L1 patterns

**Performance patterns** (caching, optimization, load-balancing):
- ❌ Represent HOW (implementation techniques), not WHAT
- ❌ Load-balancing = `orchestrator` + L3/L5 tech
- ✅ Implementation details at L3/L5, not L1 capabilities

### L1C (Cognitive) Patterns Pass the Test:

The 6 Cognitive Patterns (L1C) are a special classification within L1 because:
- ✅ Irreducible mental capabilities (knowledge, values, learning, motivation, prediction, ethics)
- ✅ Reality-agnostic (digital AI, robotic cognition, hybrid AR intelligence)
- ✅ Technology-agnostic (PyTorch, TensorFlow, symbolic AI, neuromorphic chips)
- ✅ Together form minimum sufficient set for AGI

**L1C patterns are still L1 patterns** - they just represent cognitive capabilities specifically.

---

## The 13 Critical Patterns

### 1. Agent
**What it does**: Acts autonomously based on goals and context  
**Example use**: A customer service bot that independently handles support requests

### 2. Documenter
**What it does**: Creates and maintains documentation from patterns and code  
**Example use**: Auto-generating API docs from SPL pattern definitions

### 3. Entity
**What it does**: Represents structure, state, and identity  
**Example use**: A user profile with properties, lifecycle, and persistent identity

### 4. Generator
**What it does**: Creates other patterns, content, or code  
**Example use**: Generating React components from SPL pattern specifications

### 5. Hypothesis
**What it does**: Creates and tests assumptions and predictions  
**Example use**: Predicting customer churn with testable confidence scores

### 6. Monitor
**What it does**: Observes state changes and triggers responses  
**Example use**: Watching system metrics and alerting on anomalies

### 7. Orchestrator
**What it does**: Coordinates multiple patterns toward a common goal  
**Example use**: Managing a multi-step workflow across different services

### 8. Policy-Guard
**What it does**: Enforces rules, constraints, and governance policies  
**Example use**: Ensuring GDPR compliance before processing user data

### 9. Reality-Bridge
**What it does**: Connects different realities (digital ↔ physical ↔ hybrid)  
**Example use**: Syncing a digital twin with physical factory sensors

### 10. Repository-Organizer
**What it does**: Manages storage, retrieval, and organization of patterns  
**Example use**: Version control and dependency management for SPL patterns

### 11. Resolver
**What it does**: Resolves conflicts, dependencies, and ambiguities  
**Example use**: Choosing the best option from multiple API responses

### 12. Translator
**What it does**: Transforms between representations while preserving meaning  
**Example use**: Converting YAML patterns to executable Python code

### 13. Uncertainty-Handler
**What it does**: Manages probabilistic information and incomplete knowledge  
**Example use**: Calculating confidence intervals for AI predictions

### 14. Validator
**What it does**: Verifies patterns against defined criteria  
**Example use**: Checking that a pattern meets security requirements

---

## Why These 14?

These patterns represent the **minimum sufficient set** of capabilities needed to build any intelligent system. You can create millions of specialized patterns by:

- **Composing** them (validator + uncertainty-handler = probabilistic validator)
- **Specializing** them (translator → code-translator → python-translator)
- **Combining** them (orchestrator + agent + monitor = autonomous workflow)

With just 13 patterns, you can create **2^13 = 8,192 distinct combinations** before even considering multi-pattern compositions.

---

## Critical Patterns vs. Cognitive Patterns

| Aspect | Critical Patterns | Cognitive Patterns |
|--------|------------------|-------------------|
| **Focus** | What systems **do** | How systems **think** |
| **Nature** | Functional/structural | Mental/behavioral |
| **Role** | Skeletal structure | Neural system |
| **Count** | 13 patterns (L1) | 6 patterns (L1C) |
| **Example** | Translator, Validator | Value-system, Ethical-reasoning |

**Critical Patterns** are like the skeleton and muscles—they provide structure and action.  
**Cognitive Patterns** are like the brain—they provide reasoning and intelligence.

**Together**, they create complete AGI-capable systems.

---

## Key Properties

### Reality-Agnostic
Critical Patterns work the same whether you're:
- Processing digital data in the cloud
- Controlling physical robots in a factory
- Managing hybrid digital-physical systems (BIM ↔ construction)

### Three Pillars
Every Critical Pattern implements:
- **Contract** (LLM Layer): Goal, inputs, outputs, guarantees
- **Execution** (Runtime Layer): Steps, validation, monitoring
- **Guarantees** (Culture Layer): Safety, ethics, human protection

### Composable
You can combine patterns freely:

```yaml
# Horizontal composition (same layer)
workflow:
  uses:
    - pattern/translator:v2.3
    - pattern/validator:v2.3

# Vertical composition (inheritance)
digital_validator:
  inherits_from: pattern/validator:v2.3
  reality: digital

# Hybrid composition
validated_translator:
  inherits_from: pattern/translator:v2.3
  uses:
    - pattern/validator:v2.3
    - pattern/uncertainty-handler:v2.3
```

---

## Example: Validator Critical Pattern

```yaml
version: 2.3
schema: spl.meta-pattern.v2.3
id: "pattern/validator:v2.3"
kind: critical-pattern

info:
  title: "Validator Pattern"
  description: "Verifies patterns against defined criteria"

contract:
  goal: "Verify that data/patterns meet specified constraints"
  inputs:
    - name: data
      type: any
      required: true
    - name: constraints
      type: object
      required: true
  outputs:
    - name: validation_result
      type: object
      schema:
        valid: boolean
        violations: array
        confidence: number  # Truth score
  
  guarantees:
    - "All constraints are checked"
    - "Violations are clearly reported"
    - "Confidence score reflects certainty"

execution:
  steps:
    - Load constraints
    - Check each constraint against data
    - Calculate truth score
    - Report violations

guarantees:
  safety: "Cannot modify data during validation"
  ethics: "Respects privacy constraints"
  human_protection: "Alerts on dangerous violations"
```

---

## How to Use Critical Patterns

### 1. **Start with a Critical Pattern**
Choose the pattern that matches your need:
- Need to transform data? → Translator
- Need to verify correctness? → Validator
- Need autonomous behavior? → Agent

### 2. **Specialize for Your Reality**
Add reality-specific details:
```yaml
digital_translator:
  inherits_from: pattern/translator:v2.3
  reality: digital
  formats: [json, yaml, xml]
```

### 3. **Compose for Complexity**
Combine patterns to solve complex problems:
```yaml
ai_governance_pipeline:
  uses:
    - pattern/validator:v2.3        # Check safety
    - pattern/uncertainty-handler:v2.3  # Calculate confidence
    - pattern/policy-guard:v2.3     # Enforce rules
    - pattern/monitor:v2.3          # Watch for drift
```

### 4. **Implement and Test**
Each pattern comes with:
- Clear contracts (what it does)
- Validation criteria (how to test it)
- Composition rules (how to combine it)

---

## Architectural Placement

```
L0: Meta-Pattern (self-describing foundation)
    ↓
L1: Critical Patterns (13 universal capabilities) ← YOU ARE HERE
    │
    ├─→ L1C: Cognitive Patterns (6 patterns for AGI - special classification)
    │   Example: knowledge-representation, value-system, ethical-reasoning
    │
    ├─→ L1 can have other classifications (L1I, L1S, etc.)
    │
    ↓ (all L1 patterns specialize to realities)
L2: Reality Patterns (digital, physical, hybrid)
    │   Examples: knowledge-representation/digital, value-system/physical
    ↓
L3: Technology Patterns (React, Django, ROS, Unity, PyTorch, etc.)
    │   Examples: knowledge-representation/digital/pytorch
    ↓
L4: Products (reusable contract definitions)
    ↓
L5: Solutions (complete implementations)
```

**Critical Patterns (L1)** are 13 universal capabilities.  
**L1C** is a *classification* of 6 L1 patterns that together enable AGI.  
**L1C patterns still flow through L2→L3→L4→L5** like any other L1 pattern.  
Example: `knowledge-representation` (L1C) → `knowledge-representation/digital` (L2) → `knowledge-representation/digital/pytorch` (L3)

---

## What This Means

**Critical Patterns are not:**
- AI models (they work with any LLM)
- Programming languages (they're specifications)
- Locked to one reality (they work everywhere)

**Critical Patterns are:**
- The fundamental vocabulary of intelligent systems
- Composable building blocks with truth scores
- The bridge between abstract meta-pattern and concrete implementations

---

## Bottom Line

**13 Critical Patterns** define what intelligent systems do.  
**6 Cognitive Patterns** define how intelligent systems think.  
**Together** = AGI-capable systems with verifiable truth scores.

Start with Critical Patterns when you need structure and action.  
Add Cognitive Patterns when you need reasoning and intelligence.  
Compose them freely to build anything.

---

*For the complete specification of each Critical Pattern, see `patterns/critical-patterns/*/v2.3/*.yaml`*
