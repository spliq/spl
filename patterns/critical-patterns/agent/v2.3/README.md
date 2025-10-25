# Agent (Core)

**Pattern ID**: `template/agent:v2.3`  
**Version**: 2.3  
**Layer**: 1  
**Inherits From**: `spl/meta-pattern:v2.3`  
**Status**: active

Core reality-agnostic agent template that perceives, decides, and acts toward goals.

YAML: `critical-patterns/agent/v2.3/agent.yaml`


## Overview

**Purpose**: Autonomously perceive environment, make decisions, and execute actions to achieve defined goals

**Context**: 
- Layer 1 core agent template
- Reality-agnostic pattern
- Foundation for autonomous systems

**Warnings**:
- Must maintain goal alignment
- Must preserve safety constraints
- Must be accountable for actions
- Must adapt based on feedback


## Contract

**Goal**: Autonomously perceive environment, make decisions, and execute actions to achieve defined goals

### Inputs

| Name | Type | Required | Description |
| --- | --- | --- | --- |
| goal | object | True | Goal specification with success criteria |
| environment | object | True | Current environment state |
| capabilities | array | True | Available actions and tools |

### Outputs

| Name | Type | Description |
| --- | --- | --- |
| action_result | object | Result of agent's actions |

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
