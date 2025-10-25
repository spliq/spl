# Generator (Core)

**Pattern ID**: `template/generator:v2.3`  
**Version**: 2.3  
**Layer**: 1  
**Inherits From**: `spl/meta-pattern:v2.3`  
**Status**: active

Core reality-agnostic generator template that transforms specifications into concrete artifacts.

YAML: `critical-patterns/generator/v2.3/generator.yaml`


## Overview

**Purpose**: Transform abstract specifications into concrete artifacts that embody the original design intent

**Context**: 
- Layer 1 core generator template
- Reality-agnostic pattern
- Foundation for all generator types

**Warnings**:
- Must preserve intent from specification
- Must be template-driven
- Must be repeatable with same inputs
- Generated artifacts must manifest correctly in target reality


## Contract

**Goal**: Transform abstract specifications into concrete artifacts that embody the original design intent

### Inputs

| Name | Type | Required | Description |
| --- | --- | --- | --- |
| specification | object | True | Input specification defining what to generate |
| templates | array | True | Transformation patterns to apply |
| parameters | object | False | Generation parameters for customization |

### Outputs

| Name | Type | Description |
| --- | --- | --- |
| artifacts | array | Generated concrete artifacts |
| metadata | object | Information about generation process |

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
