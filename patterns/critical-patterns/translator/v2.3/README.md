# Translator (Core)

**Pattern ID**: `template/translator:v2.3`  
**Version**: 2.3  
**Layer**: 1  
**Inherits From**: `spl/meta-pattern:v2.3`  
**Status**: active

Core reality-agnostic translator template for bidirectional domain bridges.

YAML: `critical-patterns/translator/v2.3/translator.yaml`


## Overview

**Purpose**: Bridge two domains with a reversible, semantics-preserving mapping

**Context**: 
- Core Layer 1 template - reality agnostic, enables specialization at L2+

**Warnings**:
- Ensure bidirectionality or explicit inverse
- Validate semantic preservation


## Contract

**Goal**: Bridge two domains with a reversible, semantics-preserving mapping

### Inputs

| Name | Type | Required | Description |
| --- | --- | --- | --- |
| domain_A | any | True | Source domain data/structure |
| domain_B | any | True | Target domain data/structure |

### Outputs

| Name | Type | Description |
| --- | --- | --- |
| mapping_result | object | Result of bidirectional mapping with validation |

### Guarantees

No guarantees specified


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

No examples provided.


## Inheritance

This pattern inherits from: `spl/meta-pattern:v2.3`
