# What is the Meta-Pattern?

Version: 2.3  
Owner: SPLiQ team  
License: Apache 2.0  
Status: Public explainer (publishable)  
Audience: Developers, architects, and anyone wanting to understand SPL's foundation

---

## Executive Summary

The Meta-Pattern is the self-describing foundation of SPL—the L0 layer that defines the structure ALL patterns must follow. It's a pattern that describes what patterns are, making SPL self-consistent and verifiable from the ground up.

---

## Definition

The **Meta-Pattern** is Layer 0 (L0) of SPL—the foundational specification that:

1. **Defines what a pattern is** - The schema all patterns must follow
2. **Describes itself** - It's a pattern that follows its own rules (self-describing)
3. **Enables composition** - Provides the structure for patterns to work together
4. **Enforces truth scores** - Requires verifiability in all patterns
5. **Implements the three pillars** - Contract, Execution, Guarantees

**Think of the Meta-Pattern as the "DNA" of SPL** - it contains the genetic code that all other patterns inherit.

---

## The L0 Test: What Makes the Meta-Pattern?

There is only ONE pattern at L0 because it must satisfy these unique requirements:

### 1. ✅ **Self-describing**
   - The Meta-Pattern must describe itself
   - It follows its own rules and schema
   - Cannot depend on external definitions
   - Example: The Meta-Pattern's `schema` field points to itself

### 2. ✅ **Foundation for all other patterns**
   - Every L1, L2, L3, L4, L5 pattern inherits from L0
   - Defines the required structure (contract, execution, guarantees)
   - Provides the basis for composition and validation
   - Without L0, no other patterns can exist

### 3. ✅ **Minimal and complete**
   - Contains only the essential fields needed by all patterns
   - Nothing less (patterns couldn't function)
   - Nothing more (would force unnecessary complexity)
   - Achieves balance between flexibility and rigor

### 4. ✅ **Version-controlled and evolvable**
   - The Meta-Pattern itself has versions (v2.3)
   - Changes to SPL happen by evolving L0
   - Backward compatibility maintained through versioning
   - All patterns inherit the version discipline

### 5. ✅ **Enables truth scoring**
   - Requires all patterns to produce verifiable outputs
   - Guarantees must be testable
   - Creates the foundation for trustworthy AI
   - Truth scores propagate through pattern composition

---

## Why There's Only One L0

**Patterns that don't belong at L0:**

**Base classes or parent types**:
- ❌ Not self-describing (would need something above them)
- ✅ Belong at L1 (like `entity` pattern)

**Framework specifications**:
- ❌ Technology-specific (REST, GraphQL, etc.)
- ✅ Belong at L3 (technology patterns)

**Schema definitions**:
- ❌ Only one schema needed: the Meta-Pattern itself
- ✅ Other schemas are L1+ patterns following the Meta-Pattern

The Meta-Pattern is **necessarily unique** - having multiple L0 patterns would break self-consistency.

---

## Why It's Self-Describing

The Meta-Pattern is unique: **it describes itself**.

```yaml
# The Meta-Pattern describes its own structure
id: "spl/meta-pattern:v2.3"
schema: spl.meta-pattern.v2.3  # ← It follows itself!
kind: pattern

# It has the same fields it requires from all patterns
contract: { ... }
execution: { ... }
guarantees: { ... }
```

This self-reference means:
- SPL has no "turtles all the way down" problem
- The foundation is verifiable by its own rules
- Changes to SPL must update the Meta-Pattern itself

---

## The Three Core Sections

Every pattern (including the Meta-Pattern) has three required sections:

### 1. Contract
**What the pattern does**

```yaml
contract:
  goal: "What this pattern achieves"
  inputs:
    - name: input_name
      type: input_type
      required: true/false
  outputs:
    - name: output_name
      type: output_type
      schema: { ... }
```

**Why it matters:** Clear contracts make patterns composable and verifiable.

### 2. Execution
**How the pattern does it**

```yaml
execution:
  steps:
    - "Step 1: Do this"
    - "Step 2: Then this"
    - "Step 3: Finally this"
```

**Why it matters:** Explicit execution means you can trace how results are produced.

### 3. Guarantees
**How well it does it**

```yaml
guarantees:
  success_criteria:
    - "Result meets quality threshold"
    - "No harmful side effects"
  truth_score_requirements:
    minimum: 0.80
  safety:
    - "Cannot access unauthorized data"
  ethics:
    - "Respects user privacy"
```

**Why it matters:** Guarantees enable verification and trust.

---

## Required Fields

The Meta-Pattern defines these fields as **mandatory** for all patterns:

### Identity Fields
```yaml
id: "namespace/type/name:v2.3"    # Unique identifier
version: 2.3                       # Semantic version
schema: spl.meta-pattern.v2.3      # Which meta-pattern version
kind: pattern                      # Type of pattern
```

### Information Fields
```yaml
info:
  title: "Human-readable name"
  description: "What this pattern does"
  owners: ["team-name"]
  tags: ["category", "domain"]
```

### Relationship Fields
```yaml
relations:
  inherits_from: "parent-pattern:v2.3"   # Inheritance
  implements: "product-contract:v2.3"     # Contract implementation
  uses:                                   # Dependencies
    - id: "dependency:v2.3"
      reason: "Why we need this"
```

### Core Sections (mentioned above)
```yaml
contract: { ... }   # REQUIRED
execution: { ... }  # REQUIRED
guarantees: { ... } # REQUIRED
```

---

## What the Meta-Pattern Enables

### 1. Validation
Every pattern can be validated against the Meta-Pattern:

```bash
# Check if a pattern is valid
spl-validator validate my-pattern.yaml

# Result:
✓ Has required fields (id, version, schema, kind)
✓ Contract is well-formed
✓ Execution steps are clear
✓ Guarantees are verifiable
✓ Relationships are valid
```

### 2. Composition
Patterns can be safely composed because they share a common structure:

```yaml
# Pattern A and Pattern B both follow meta-pattern
# So they can be composed
composed_pattern:
  uses:
    - pattern-a:v2.3
    - pattern-b:v2.3
```

### 3. Evolution
The Meta-Pattern can evolve with clear version control:

```yaml
# Version history
versions:
  - version: v2.3
    changes:
      - "Added 'uses' relationship for dependencies"
      - "Simplified relationship model"
  - version: v2.2
    changes:
      - "Renamed 'pillars' to 'contract'"
```

### 4. Interoperability
All SPL tools understand patterns because they all follow the Meta-Pattern:
- Validators know what to check
- Generators know what to create
- Translators know how to transform
- Orchestrators know how to execute

---

## The Six-Layer Architecture

The Meta-Pattern is L0—the foundation for all other layers:

```
L0: Meta-Pattern ← YOU ARE HERE
    ↓ (defines structure for)
L1: Critical Patterns (13 universal capabilities)
    ↓ (specialize to)
L2: Reality Patterns (digital, physical, hybrid)
    ↓ (implement with)
L3: Technology Patterns (React, Django, etc.)
    ↓ (provide contracts as)
L4: Products (reusable contract definitions)
    ↓ (implemented by)
L5: Solutions (complete implementations with code)
```

**Everything inherits from L0.** Even L1 Critical Patterns must follow the Meta-Pattern.

---

## Example: The Meta-Pattern Itself

Here's a simplified view of the Meta-Pattern describing itself:

```yaml
version: 2.3
schema: spl.meta-pattern.v2.3
id: "spl/meta-pattern:v2.3"
kind: pattern

info:
  title: "SPL Meta-Pattern"
  description: "The self-describing foundation of all patterns"
  owners: ["spl-core-team"]

contract:
  goal: "Define the structure and requirements for all SPL patterns"
  inputs:
    - name: pattern_definition
      type: yaml
      description: "A pattern to validate"
  outputs:
    - name: validation_result
      type: object
      schema:
        valid: boolean
        errors: array
        truth_score: number

execution:
  steps:
    - "Parse pattern YAML"
    - "Check required fields exist"
    - "Validate contract structure"
    - "Verify execution steps"
    - "Confirm guarantees are testable"
    - "Calculate truth score"

guarantees:
  success_criteria:
    - "All required fields are present"
    - "Relationships are valid"
    - "Contract is well-formed"
  truth_score_requirements:
    minimum: 1.0  # Meta-pattern must be perfect
  safety:
    - "Cannot modify pattern definitions"
    - "Only validates, never executes"

# The meta-pattern has version history
versions:
  - version: v2.3
    changes:
      - "BREAKING: Replaced spl_dependencies with 'uses'"
      - "ADDED: implements field for contract implementation"
      - "Established canonical three-relationship model"
  - version: v2.2
    changes:
      - "Renamed pillars → contract"
      - "Renamed evaluation → guarantees"
```

---

## Why Self-Description Matters

### 1. No External Dependencies
SPL doesn't need an external schema language (like JSON Schema). It describes itself.

### 2. Verifiable Foundation
You can verify the Meta-Pattern using its own rules:

```bash
# Validate the meta-pattern against itself
spl-validator validate patterns/meta-pattern/v2.3/meta-pattern.yaml

# It will check itself and confirm it's valid
✓ Meta-pattern is self-consistent
```

### 3. Evolution Without Breaking
When SPL evolves, the Meta-Pattern evolves with it. Old patterns stay valid under old meta-patterns.

### 4. Trust Through Transparency
The entire system is open to inspection. No hidden rules.

---

## Key Properties

### Minimal
The Meta-Pattern defines **only what's necessary**:
- Required fields for identity
- Structure for contracts
- Format for execution
- Framework for guarantees
- Rules for relationships

Everything else is optional or defined by specific pattern types.

### Extensible
Patterns can add fields beyond the Meta-Pattern:

```yaml
# Valid pattern with custom fields
id: "my-pattern:v2.3"
schema: spl.meta-pattern.v2.3
# ... required fields ...

custom_field: "This is allowed!"
my_extension:
  extra_data: "Also fine"
```

### Enforceable
The Meta-Pattern provides validation criteria:

```yaml
# This will FAIL validation
id: "bad-pattern"  # Missing version!
# Missing: version, schema, kind, contract, execution, guarantees
```

---

## How Patterns Inherit from Meta-Pattern

All patterns inherit the Meta-Pattern's structure:

```
Meta-Pattern (L0)
    ↓
    requires: [id, version, schema, kind, contract, execution, guarantees]
    ↓
Critical Pattern (L1)
    ↓
    adds: [specialization for validator/agent/translator/etc.]
    ↓
Reality Template (L2)
    ↓
    adds: [reality context: digital/physical/hybrid]
    ↓
Technology Template (L3)
    ↓
    adds: [technology specifics: React/Django/etc.]
    ↓
Product (L4)
    ↓
    adds: [contract details, no implementation]
    ↓
Solution (L5)
    ↓
    adds: [actual code implementation]
```

**Every pattern is valid because it follows the Meta-Pattern.**
---

## Architectural Placement

```
L0: Meta-Pattern ← YOU ARE HERE
    ↓ (defines structure for all patterns)
L1: Critical Patterns (13 universal capabilities)
    │   L1C: Cognitive (6 patterns for AGI - classification, not layer)
    │   L1I: Infrastructure (future classification)
    │   L1S: Security (future classification)
    ↓ (all L1 patterns flow through)
L2: Reality Patterns (digital, physical, hybrid)
    ↓
L3: Technology Patterns (React, Django, ROS, Unity, PyTorch, etc.)
    ↓
L4: Products (reusable contract definitions)
    ↓
L5: Solutions (complete implementations)
```

**Meta-Pattern (L0)** defines the structure ALL patterns follow.  
**L1C, L1I, L1S** are classifications within L1, not separate layers.  
Every pattern flows L0→L1→L2→L3→L4→L5 regardless of classification.

---

## What This Means

**The Meta-Pattern is not:**
- A programming language (it's a specification)
- Complex (it's intentionally minimal)
- Fixed forever (it evolves with versions)

**The Meta-Pattern is:**
- The foundation of all SPL patterns
- Self-describing and self-validating
- The reason SPL patterns are composable
- The source of truth scores and verifiability

---

## Try It Yourself

1. Look at the Meta-Pattern: `patterns/meta-pattern/v2.3/meta-pattern.yaml`
2. Notice it follows its own rules
3. Pick any other pattern in the registry
4. Verify it has the required Meta-Pattern fields
5. See how validation works: `./tools/validate.py <pattern-file>`

---

## Bottom Line

**The Meta-Pattern is L0**—the self-describing foundation that makes SPL patterns:
- Composable (common structure)
- Verifiable (clear contracts and guarantees)
- Evolvable (version-controlled schema)
- Trustworthy (transparent and testable)

Without the Meta-Pattern, SPL would be a collection of inconsistent patterns.  
**With the Meta-Pattern, SPL is a rigorous, verifiable, composable system.**

Every pattern inherits from L0.  
Every pattern follows the same rules.  
Every pattern produces truth scores.

**That's the power of the Meta-Pattern.**

---

*For the complete specification, see `patterns/meta-pattern/v2.3/meta-pattern.yaml`*  
*For technical details, see `patterns/meta-pattern/v2.3/README.md`*
