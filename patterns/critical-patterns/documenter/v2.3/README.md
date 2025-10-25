# Documentation Critical Pattern

**Pattern ID**: `template/documenter:v2.3`  
**Version**: 2.3  
**Layer**: 1  
**Inherits From**: `spl/meta-pattern:v2.3`  
**Status**: active

Foundational template defining how SPL patterns are documented—validatable, versioned, and composable.

YAML: `critical-patterns/documenter/v2.3/documenter.yaml`


## Overview

**Purpose**: Define the foundational contract for all SPL documentation patterns. Ensures documentation is structured, validated, versioned, and can be automatically generated from pattern definitions.

**Context**: 
- Documentation is not an afterthought - it's a pattern
- All patterns (L1-L5) must have associated documentation
- Documentation inherits structure and validation from this pattern

**Warnings**:
- All documentation patterns MUST inherit from this critical pattern
- Documentation completeness is validated automatically
- Missing required sections will fail validation


## Contract

**Goal**: Define the foundational contract for all SPL documentation patterns. Ensures documentation is structured, validated, versioned, and can be automatically generated from pattern definitions.

### Inputs

| Name | Type | Required | Description |
| --- | --- | --- | --- |
| pattern_yaml | object | True | The pattern YAML file to document |
| documentation_context | object | False | Additional context for documentation generation (examples, use cases, etc.) |

### Outputs

| Name | Type | Description |
| --- | --- | --- |
| documentation_artifact | object | Generated documentation in specified format |

### Guarantees

- **Documentation completeness**: All required sections are present
  - Validation: Check for required_sections in generated documentation
- **Link integrity**: All pattern references resolve correctly
  - Validation: Validate all pattern IDs exist in registry
- **Code example validity**: Code examples are syntactically correct
  - Validation: Parse and validate code blocks
- **Version consistency**: Documentation version matches pattern version
  - Validation: Compare doc version with pattern version


## Usage

Basic usage example:

```python
# Import the pattern
from spl.patterns import load_pattern

# Use the pattern
pattern = load_pattern("pattern-id:version")
result = pattern.execute(inputs)
```


## Examples

### Basic Documentation Generation

Generate markdown documentation for a pattern

```python
# Load pattern
pattern = load_pattern("critical/resolver:v2.3")

# Generate documentation
docs = generate_documentation(
    pattern=pattern,
    format="markdown",
    include_examples=True
)

# Validate completeness
validation = validate_documentation(docs)
assert validation.complete == True

# Write to file
write_file("resolver-documentation.md", docs.content)

```

### Documentation Validation

Validate documentation completeness

```python
# Load existing documentation
docs = load_documentation("patterns/critical-patterns/resolver/v2.3/README.md")

# Validate against requirements
result = validate_documentation_completeness(
    documentation=docs,
    pattern_id="critical/resolver:v2.3"
)

# Check results
if not result.complete:
    print(f"Missing sections: {result.missing_sections}")
    print(f"Warnings: {result.warnings}")

```



## Inheritance

This pattern inherits from: `spl/meta-pattern:v2.3`
