# SPL Versioning Policy

Version: 2.3  
Owner: SPLiQ team  
License: Apache 2.0  
Status: Public documentation  
Audience: All SPL contributors, developers, and users

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
**Current Meta-Pattern**: `v2.3` → **All L5 solutions MUST use `v2.3.x` format** (e.g., `v2.3.0`, `v2.3.1`)

| Component | Value | Meaning |
|-----------|-------|---------|
| **Major** | `2` | Meta-pattern major version |
| **Minor** | `3` | Meta-pattern minor version |
| **Patch** | `0+` | Solution-specific revision |

**Examples**:
```yaml
# ✅ CORRECT - Aligned with meta-pattern v2.3
id: "solution/validator/registry-validator:v2.3.0"
version: 2.3.0

# ✅ CORRECT - Bug fix release
id: "solution/validator/registry-validator:v2.3.1"
version: 2.3.1

# ❌ WRONG - Not aligned with meta-pattern
id: "solution/validator/registry-validator:v1.0.0"
version: 1.0.0

# ❌ WRONG - Missing patch version
id: "solution/validator/registry-validator:v2.3"
version: 2.3
```

---

## Directory Structure Requirements

### Repository Structure

The SPL GitHub repository uses this structure:

```
patterns/
├── meta-pattern/
│   └── v2.3/
│       ├── meta-pattern.yaml
│       └── README.md
├── critical-patterns/          # L1 patterns
│   └── {pattern-name}/         # e.g., validator, translator, agent
│       └── v2.3/
│           ├── {pattern-name}.yaml
│           └── README.md
├── cognitive-patterns/         # L1C patterns  
│   └── {pattern-name}/         # e.g., value-system, motivation
│       └── v2.3/
│           ├── {pattern-name}.yaml
│           └── README.md
└── pattern-index-v2.3.yaml
```

**Note**: L0, L1, and L1C use two-part versioning (`v2.3`). The actual repository structure uses descriptive folder names (`critical-patterns`, `cognitive-patterns`) rather than generic layer indicators.

---

## Version Evolution Rules

### When to Bump Patch Version (L5 Only)

Increment patch version (`v2.3.0` → `v2.3.1`) when:

- Bug fixes in implementation
- Performance improvements
- Documentation updates
- Test improvements
- No API/contract changes
- Fully backward compatible

### When Meta-Pattern Version Changes

When meta-pattern upgrades (e.g., `v2.3` → `v2.4`):

**L0-L4 Patterns**:

- Create new `v2.4/` directory
- Update `version: 2.4`
- Update `id: ".../:v2.4"`

**L5 Solutions**:

- Create new `v2.4.0/` directory
- Update `version: 2.4.0`
- Update `id: ".../:v2.4.0"`
- Reset patch to `0`

---

## Validation Rules

The registry-validator enforces these rules:

Rule 1: L5 Version Alignment
    **Check**: L5 solution versions MUST start with current meta-pattern version.

Rule 2: Directory Name Match
    **Check**: Directory name MUST match pattern version.

```
Example pattern ID: solution/validator/registry-validator:v2.3.0
Expected directory: .../registry-validator/v2.3.0/
Actual directory: Must match exactly
```

---

## Migration Guide

### Migrating Solutions When Meta-Pattern Version Changes

When the meta-pattern version changes (e.g., from `v2.3` to `v2.4`), solutions must be migrated:

**Step 1: Create New Version Directory**

```bash
# Example: Migrating from v2.3.x to v2.4.0
# Old location
patterns/solutions/{type}/{name}/v2.3.5/

# New location (create this)
patterns/solutions/{type}/{name}/v2.4.0/
```

**Step 2: Copy and Update Pattern Files**

```bash
# Copy all files
cp -r v2.3.5/* v2.4.0/

# Update pattern YAML
vim v2.4.0/solution.yaml
```

**Step 3: Update Pattern Fields**

```yaml
# Change from:
version: 2.3.5
id: "solution/{type}/{name}:v2.3.5"
schema: spl.meta-pattern.v2.3

# Change to:
version: 2.4.0
id: "solution/{type}/{name}:v2.4.0"
schema: spl.meta-pattern.v2.4
```

**Step 4: Update Implementation References**

Update pyproject.toml, README.md, etc. to reflect new version

**Step 5: Regenerate Pattern Index**

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

## Enforcement

SPL has designed solutions to enforce versioning restrictions programmatically. The registry includes validation capabilities that check:

- Version format compliance (two-part for L0-L4, three-part for L5)
- Meta-pattern version alignment for solutions
- Directory name and pattern ID consistency
- Schema version compatibility

When validation errors are detected, the system provides specific guidance on how to correct versioning issues.

---

## Quick Reference

| What | Format | Current Example |
|------|--------|-----------------|
| **Meta-pattern** | `v{major}.{minor}` | `v2.3` |
| **Critical Pattern (L1)** | `v{major}.{minor}` | `v2.3` |
| **Template (L2-L3)** | `v{major}.{minor}` | `v2.3` |
| **Product (L4)** | `v{major}.{minor}` | `v2.3` |
| **Solution (L5)** | `v{major}.{minor}.{patch}` | `v2.3.0`, `v2.3.1` |

**Remember**:
- L0-L4 patterns use two-part versioning (`v2.3`) aligned with meta-pattern
- L5 solutions use three-part versioning (`v2.3.0`) with first two parts aligned to meta-pattern
