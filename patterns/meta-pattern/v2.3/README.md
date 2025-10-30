# SPL Meta-Pattern v2.3

Version: 2.3  
Owner: SPLiQ team  
License: Apache 2.0

> **The Foundation**: Defines the structure and semantics for all patterns in the Semantic Pattern Language

## Overview

The Meta-Pattern is the bedrock of SPL—the pattern that defines all other patterns. It establishes the schema, rules, and relationships that enable composition across realities (digital, physical, hybrid) and layers (L0-L5) while preserving Greg's four pillars of pattern definition.

**Version 2.3** introduces a canonical relationship model with three core relationship types, replacing the previous `spl_dependencies` field with a richer, more expressive system.

## 🎯 Purpose

- **Define** the minimal structure that all SPL patterns must follow
- **Enable** composition and inheritance across layers and realities
- **Preserve** Greg's 4-pillar architecture (contract, guarantees, extension_points, inheritance)
- **Enforce** clear relationship semantics for template inheritance, contract implementation, and runtime dependencies
- **Support** AI-oriented pattern development with semantic clarity

## 🏗️ Architecture

### The Three Core Relationships

SPL v2.3 establishes three fundamental relationship types:

```yaml
relations:
  # 1. TEMPLATE INHERITANCE (Structure)
  inherits_from: "template/parent:v2.3"
  
  # 2. CONTRACT IMPLEMENTATION (Behavior - L5 only)
  implements: "product/contract:v2.3"
  
  # 3. RUNTIME DEPENDENCIES (Usage)
  uses:
    - id: "template/helper:v2.3"
      local: true
      purpose: "Provides utility functions"
```

#### 1. Template Inheritance (`inherits_from`)

- **Purpose**: Defines structural inheritance chain
- **Cardinality**: Single parent (string, not array)
- **Required in**: L1-L5 patterns
- **Omitted in**: L0 (meta-pattern is self-defining)
- **Creates**: Vertical inheritance path through layers

**Example**:
```yaml
# L5 solution inherits from L3 template
relations:
  inherits_from: "template/validator/digital/code-validator:v2.3"
```

#### 2. Contract Implementation (`implements`)

- **Purpose**: Declares which L4 product contract this L5 solution fulfills
- **Cardinality**: Exactly ONE product (string, not array)
- **Required in**: L5 (solution) patterns ONLY
- **Prohibited in**: L0-L4 patterns
- **Creates**: Convergent inheritance with dual paths:
  - **Template path**: L5 → L3 → L2 → L1 → L0 (via `inherits_from`)
  - **Contract path**: L5 → L4 → L3 → L2 → L1 → L0 (via `implements` + `inherits_from`)

**Example**:
```yaml
# L5 solution implements L4 product contract
relations:
  implements: "product/validator/python-code-validator:v2.3"
  inherits_from: "template/validator/digital/code-validator:v2.3"
```

#### 3. Runtime Dependencies (`uses`)

- **Purpose**: Declares patterns used during execution
- **Cardinality**: Array of dependency objects
- **Optional in**: Any layer (L0-L5)
- **Supports**: Local patterns (same registry) and external patterns (other repositories)

**Example - Local Dependency**:
```yaml
relations:
  uses:
    - id: "solution/translator/pattern-to-code:v2.3"
      reason: "Pattern contract interpretation"
      purpose: "Interprets YAML patterns to extract structural requirements"
      scope: runtime
      local: true
```

**Example - External Dependency**:
```yaml
relations:
  uses:
    - id: "template/custom-validator:v1.0"
      reason: "Specialized validation logic"
      purpose: "Validates domain-specific constraints"
      scope: optional
      external:
        organization: "PrintAI"
        repository: "custom-patterns"
        url: "https://github.com/PrintAI/custom-patterns"
        branch: "main"
        path: "patterns/validators"
```

## 📋 Required Fields

Every SPL pattern must include:

| Field | Type | Description |
|-------|------|-------------|
| `version` | string | Semantic version (e.g., "2.3") |
| `schema` | string | Schema identifier (e.g., "spl.meta-pattern.v2.3") |
| `id` | string | Globally unique identifier (e.g., "spl/meta-pattern:v2.3") |
| `kind` | string | Pattern type (meta-pattern, template, product, solution) |
| `info` | object | Title, description, owners, tags |
| `contract` | object | Greg's 4-pillar contract (goal, inputs, outputs, context, warnings) |
| `relations` | object | Inheritance, implementation, and dependencies |
| `execution` | object | Execution steps and lifecycle |
| `guarantees` | object | Success criteria, metrics, validation hooks |
| `extension_points` | object | Explicit extension points for inheritance |

## 🔄 Layer-Specific Rules

The meta-pattern enforces different relationship requirements at each layer:

### L0: Meta-Pattern
- ❌ No `inherits_from` (self-defining)
- ❌ No `implements` (foundation layer)
- ✅ May have `uses` (optional)

### L1: Critical Patterns
- ✅ Must have `inherits_from` → spl/meta-pattern:v2.3
- ❌ No `implements` (foundational templates)
- ✅ May have `uses` (optional)

### L1C: Cognitive Patterns
- ✅ Must have `inherits_from` → meta-pattern:v2.3
- ❌ No `implements` (foundational templates)
- ✅ May have `uses` (optional)

### Future Layers (L2-L5)
The meta-pattern supports additional layers for reality-specific templates (L2), technology implementations (L3), products (L4), and solutions (L5). These will follow similar inheritance rules with layer-appropriate constraints.

## 🎨 Extension Points

The meta-pattern defines explicit extension points for inheritance:

```yaml
extension_points:
  layer: true              # Enable layer-specific extensions
  pattern: true            # Enable pattern-specific extensions
  reality: true            # Enable reality-specific extensions
  self_modification:       # Enable recursive self-modification
    allowed: false         # Default: patterns cannot modify themselves
    versioning_strategy: "semantic"
    validation_required: true
    max_recursion_depth: 10
```

## 📚 Greg's Four Pillars

Every pattern inheriting from the meta-pattern includes:

### 1. **Contract** (What it does)
- `goal`: Clear statement of pattern's purpose
- `inputs`: Required and optional inputs
- `outputs`: Return format and schema
- `context`: Background and assumptions
- `warnings`: Important caveats and limitations

### 2. **Guarantees** (How well it works)
- `success_criteria`: Conditions for success
- `metrics`: Measurable indicators
- `rubric`: Pass/fail criteria
- `validation_hooks`: Pre/post validation points

### 3. **Extension Points** (How to extend it)
- Explicit points for inheritance and customization
- Layer, pattern, and reality-specific extensions
- Self-modification rules and constraints

### 4. **Inheritance Mechanism** (How it composes)
- `strategy`: Extension, override, or self-descriptive
- `composition_rules`: Rules for combining patterns
- `invariants`: Required fields and relationship rules
- `extension-rules`: What children can/cannot modify


### Migration Example

**Before (v2.2)**:
```yaml
relations:
  inherits_from: "template/validator:v2.2"
  spl_dependencies:
    - "template/translator:v2.2"
```

**After (v2.3)**:
```yaml
relations:
  inherits_from: "spl/meta-pattern:v2.3"
  implements: ''
  uses:
    - local: "critical-pattern/translator:v2.3"
      purpose: "Provides pattern translation capability"
```

## 🔍 Validation

The meta-pattern includes comprehensive validation:

```yaml
execution:
  steps:
    - Parse pattern YAML structure
    - Validate against meta-pattern schema v2.3
    - Check layer-specific relationship rules
    - Validate inherits_from chain
    - Validate implements field (when present)
    - Validate uses field schema (local/external)
    - Ensure no deprecated fields (spl_dependencies)
    - Return validation results
```

Registry validators enforce:
- ✅ All required fields present
- ✅ Correct relationship types per layer
- ✅ Valid inheritance chains
- ✅ Structured `uses` dependencies
- ❌ No deprecated `spl_dependencies` field

## 📖 Usage Example

Creating a new L1 critical pattern:

```yaml
version: '2.3'
schema: spl.meta-pattern.v2.3
id: template/my-pattern:v2.3
kind: template

info:
  title: "My Pattern"
  description: "A new critical pattern"
  owners: ["spl-core"]
  tags: ["template", "layer-1"]

relations:
  inherits_from: "spl/meta-pattern:v2.3"
  uses: []

contract:
  goal: "Define a new foundational pattern"
  return_format: "Structured pattern definition"
  warnings: []
  context: ["Builds on meta-pattern foundation"]

execution:
  steps:
    - "Validate pattern structure"
    - "Execute pattern logic"
    - "Return results"

guarantees:
  success_criteria:
    - "Pattern is valid and executable"
  rubric:
    pass: ["All validations succeed"]
    fail: ["Any validation fails"]

extension_points:
  layer: true
  pattern: true
```

## 🚀 Why It Matters

The meta-pattern is crucial because:

1. **Universal Foundation**: Every pattern in SPL inherits from this
2. **Enforced Consistency**: Guarantees structural integrity across all patterns
3. **Clear Semantics**: Three relationship types eliminate ambiguity
4. **Scalable Architecture**: Designed to support unlimited pattern growth through composition
5. **AI-Oriented**: Built for semantic understanding and automated reasoning

## 📊 Current Release

This release includes:
- **L0**: 1 meta-pattern (this document)
- **L1**: 13 critical patterns (universal capabilities)
- **L1C**: 6 cognitive patterns (AGI foundations)
- **Registry**: Pattern index v2.3

**Total**: 20 foundational patterns

These patterns form the minimal foundation for building intelligent systems. All patterns follow meta-pattern v2.3 specification.

## 🔗 Related Documentation

- [What is SPL?](../../../doc/what-is-spl.md)
- [Six Layers Architecture](../../../doc/patterns/spl-six-layers-overview.md)
- [Critical Patterns Guide](../../../doc/patterns/what-are-l1-critical-patterns.md)
- [Cognitive Patterns Guide](../../../doc/patterns/what-are-l1c-cognitive-patterns.md)

## 🤝 Contributing

The meta-pattern evolves carefully as it affects all patterns. Proposed changes should:

1. Maintain backward compatibility where possible
2. Provide clear migration paths for breaking changes
3. Include comprehensive validation rules
4. Document impact across all layers
5. Preserve Greg's four pillars

---

**Version**: 2.3  
**Status**: Active  
**Layer**: L0 (Foundation)  
**Owned by**: spl-core  
**Last Updated**: —
