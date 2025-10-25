# Entity (Core)

**Pattern ID**: `template/entity:v2.3`  
**Version**: 2.3  
**Layer**: 1  
**Inherits From**: `spl/meta-pattern:v2.3`  
**Status**: active

Core reality-agnostic entity template for representing domain concepts, objects, and things.

YAML: `critical-patterns/entity/v2.3/entity.yaml`


## Overview

**Purpose**: Represent a domain concept, object, or thing with properties, states, and behaviors

**Context**: 
- Layer 1 core entity template
- Reality-agnostic pattern
- Foundation for all entity types (physical, digital, cognitive, hybrid)
- Complements behavioral patterns (generator, validator, etc.)

**Warnings**:
- Entities represent 'what things are', not 'what patterns do'
- Must define clear identity and lifecycle boundaries
- Properties should be observable and verifiable
- States must be mutually exclusive or clearly composable


## Contract

**Goal**: Represent a domain concept, object, or thing with properties, states, and behaviors

### Inputs

| Name | Type | Required | Description |
| --- | --- | --- | --- |
| entity_specification | object | True | Specification of the entity being modeled |
| entity_context | object | False | Context in which entity exists |

### Outputs

| Name | Type | Description |
| --- | --- | --- |
| entity_model | object | Complete entity model with all specifications |

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
