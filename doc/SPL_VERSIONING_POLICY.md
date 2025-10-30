# SPL Versioning Policy

Version: 2.3  
Owner: SPLiQ team  
License: Apache 2.0  
Status: MANDATORY  
Audience: All SPL pattern creators and maintainers

---

## Executive Summary

Defines the mandatory versioning rules for all SPL patterns, ensuring alignment between pattern versions and the meta-pattern schema version.

---

## Overview

This document defines the **MANDATORY** versioning rules for all SPL patterns. These rules ensure alignment between pattern versions and the meta-pattern schema version.

## Versioning Rules by Layer

### L0-L4: Two-Part Versioning

**Format**: `v{major}.{minor}`  
**Requirement**: MUST align with meta-pattern version  
**Current**: `v2.3`

| Layer | Type | Format | Example | Notes |
|-------|------|--------|---------|-------|
| L0 | Meta-pattern | `v{major}.{minor}` | `v2.3` | Defines schema version |
| L1 | Critical Patterns | `v{major}.{minor}` | `v2.3` | Must match L0 |
| L2 | Templates | `v{major}.{minor}` | `v2.3` | Must match L0 |
| L3 | Templates | `v{major}.{minor}` | `v2.3` | Must match L0 |
| L4 | Products | `v{major}.{minor}` | `v2.3` | Must match L0 |

**Rationale**: Layers 0-4 define contracts and structures that must be synchronized with the meta-pattern schema.

---

### L5: Three-Part Aligned Versioning

**Format**: `v{meta-major}.{meta-minor}.{solution-patch}`  
**Requirement**: MUST align first two digits with meta-pattern version  
**Current Meta-Pattern**: `v2.3` → **All L5 solutions MUST use `v2.3.x` format**

| Component | Value | Meaning |
|-----------|-------|---------|
| **Major** | `2` | Meta-pattern major version |
| **Minor** | `3` | Meta-pattern minor version |
| **Patch** | `0+` | Solution-specific revision |

**Examples**:
```yaml
# ✅ CORRECT - Aligned with meta-pattern v2.3
id: "solution/validator/registry-validator:v2.3"
version: 2.3

# ❌ WRONG - Not aligned with meta-pattern
id: "solution/validator/registry-validator:v1.0"
version: 1.0
```

---

## Directory Structure Requirements

### L0-L4 Directory Structure

```
patterns/{layer}/{type}/{name}/
└── v{major}.{minor}/           # Example: v2.3/
    └── {name}.yaml
```

### L5 Directory Structure

```
patterns/solutions/{type}/{name}/
└── v{major}.{minor}/           # Example: v2.3/
    ├── solution.yaml
    ├── implementation/
    └── tests/
```

**CRITICAL**: The directory name MUST match the version in the pattern ID.

---

## Version Evolution Rules

### When Meta-Pattern Version Changes

When meta-pattern upgrades (e.g., `v2.3` → `v2.4`):

**L0-L4 Patterns**: 
- Create new `v2.4/` directory
- Update `version: 2.4`
- Update `id: ".../:v2.4"`

**L5 Solutions**:
- Create new `v2.4/` directory
- Update `version: 2.4`
- Update `id: ".../:v2.4"`

---

## Validation Rules

The registry-validator enforces these rules:

### Rule 1: L5 Version Alignment

**Check**: L5 solution versions MUST start with current meta-pattern version.

```python
# Validator logic
meta_pattern_version = "2.3"
solution_version = extract_version(solution_id)  # "v2.3"

if solution_version != meta_pattern_version:
    raise ValidationError(
        f"Solution version {solution_version} does not align "
        f"with meta-pattern v{meta_pattern_version}. "
        f"Expected v{meta_pattern_version}"
    )
```

### Rule 2: Directory Name Match

**Check**: Directory name MUST match pattern version.

```python
# Example pattern ID: solution/validator/registry-validator:v2.3
# Expected directory: .../registry-validator/v2.3/
# Actual directory: Must match exactly
```

---

## Migration Guide

### Migrating Existing v1.x Solutions

If you have solutions using `v1.0` or other non-aligned versions:

**Step 1: Create New Version Directory**
```bash
# Old location
patterns/solutions/{type}/{name}/v1.0/

# New location (create this)
patterns/solutions/{type}/{name}/v2.3/
```

**Step 2: Copy and Update Pattern Files**
```bash
# Copy all files
cp -r v1.0/* v2.3/

# Update pattern YAML
vim v2.3/solution.yaml
```

**Step 3: Update Pattern Fields**
```yaml
# Change from:
version: 1.0
id: "solution/{type}/{name}:v1.0"

# Change to:
version: 2.3
id: "solution/{type}/{name}:v2.3"
schema: spl.meta-pattern.v2.3
```

**Step 4: Update Implementation References**
```bash
# Update pyproject.toml, README.md, etc. to reflect new version
```

**Step 5: Regenerate Pattern Index**
```bash
cd patterns/solutions/generator/pattern-index-generator/v2.3/implementation
uv run python -m pattern_index_generator.cli /path/to/spl-registry --max-version 2.3
```

**Step 6: Validate**
```bash
./tools/registry-validator-errors-only
```

**Step 7: Deprecate Old Version**
```bash
# Mark old version as deprecated in CHANGELOG
echo "## v1.0 - DEPRECATED - Use v2.3 instead" >> v1.0/CHANGELOG.md
```

---

## Rationale

### Why Aligned Versioning?

1. **Schema Compatibility**: Solutions must work with specific meta-pattern schemas
2. **Dependency Clarity**: Immediately know which meta-pattern version a solution supports
3. **Migration Tracking**: Clear upgrade path when meta-pattern changes
4. **Validation Simplification**: Registry validator can enforce compatibility
5. **Documentation Clarity**: Version numbers tell the full story

### Why Same Versioning for All Layers?

1. **Consistency**: All patterns aligned with meta-pattern version
2. **Schema Compatibility**: Clear indication of supported meta-pattern
3. **Simplicity**: One version format to remember
4. **Upgrade Clarity**: Version change means meta-pattern alignment change

---

## Examples

### Correct Versioning

```yaml
# Meta-pattern v2.3
patterns/meta-pattern/v2.3/meta-pattern.yaml:
  version: 2.3
  id: "spl/meta-pattern:v2.3"

# L1 Critical Pattern
patterns/critical-patterns/validator/v2.3/validator.yaml:
  version: 2.3
  id: "template/validator:v2.3"

# L4 Product
patterns/products/validator/registry-validator/v2.3/registry-validator.yaml:
  version: 2.3
  id: "product/validator/registry-validator:v2.3"

# L5 Solution
patterns/solutions/validator/registry-validator/v2.3/registry-validator.yaml:
  version: 2.3
  id: "solution/validator/registry-validator:v2.3"
```

### Incorrect Versioning

```yaml
# ❌ L5 using v1.0 when meta-pattern is v2.3
patterns/solutions/validator/registry-validator/v1.0/registry-validator.yaml:
  version: 1.0
  id: "solution/validator/registry-validator:v1.0"
  
# ❌ Wrong meta-pattern alignment
patterns/solutions/validator/registry-validator/v2.2/registry-validator.yaml:
  version: 2.2
  id: "solution/validator/registry-validator:v2.2"
```

---

## Enforcement

### Registry Validator

The registry-validator enforces these rules:

```bash
# Run validation
./tools/registry-validator-errors-only

# Example error output
ERROR: Solution version mismatch
  Pattern: solution/validator/registry-validator:v1.0
  Issue: Solution version v1.0 does not align with meta-pattern v2.3
  Fix: Upgrade to v2.3 and update directory structure
```

### Pattern Index Generator

The pattern-index-generator will:
- Warn about non-aligned versions
- Exclude deprecated versions
- Require `--max-version 2.3` flag for v2.3 patterns

---

## Quick Reference

| What | Format | Current Example |
|------|--------|-----------------|
| **Meta-pattern** | `v{major}.{minor}` | `v2.3` |
| **Critical Pattern (L1)** | `v{major}.{minor}` | `v2.3` |
| **Template (L2-L3)** | `v{major}.{minor}` | `v2.3` |
| **Product (L4)** | `v{major}.{minor}` | `v2.3` |
| **Solution (L5)** | `v{major}.{minor}` | `v2.3` |

**Remember**: All patterns use `v2.3` format aligned with meta-pattern!

---

## Related Documentation

- [Layer Enforcement v2.3](./layer-enforcement-v2.3.md)

---

## Change Log

- v1.0 - Initial versioning policy document
  - Established mandatory L5 version alignment rule
  - Documented three-part versioning requirement
  - Added migration guide for v1.x.x solutions
  - Clarified validation rules and enforcement
