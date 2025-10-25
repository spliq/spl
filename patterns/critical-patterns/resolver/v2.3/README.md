# Resolver (Core)

**Pattern ID**: `template/resolver:v2.3`  
**Version**: 2.3  
**Layer**: 1  
**Inherits From**: `spl/meta-pattern:v2.3`  
**Status**: active

Core reality-agnostic resolver template for selection, aggregation, and reconciliation across realities.

YAML: `critical-patterns/resolver/v2.3/resolver.yaml`


## Overview

**Purpose**: Find, select, combine, or reconcile resources to satisfy requirements while maintaining system integrity

**Context**: 
- Layer 1 core resolver template
- Reality-agnostic pattern
- Foundation for both selection and aggregation capabilities
- Universal resolution interface
- Supports dependency, resource, discovery, reference, and constraint resolution

**Warnings**:
- Must be deterministic for same inputs
- Must detect all conflicts between requirements
- Must maintain compatibility across resolved resources
- Must satisfy all specified constraints
- Must provide clear failure diagnostics
- Must preserve essential properties during aggregation
- Must provide explainable decision rationale


## Contract

**Goal**: Find, select, combine, or reconcile resources to satisfy requirements while maintaining system integrity

### Inputs

| Name | Type | Required | Description |
| --- | --- | --- | --- |
| requirements | object | True | What needs to be resolved |
| context | object | False | Resolution context and environment |

### Outputs

| Name | Type | Description |
| --- | --- | --- |
| resolution_result | object | Resolution results |

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
