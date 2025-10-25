# Orchestrator (Core)

**Pattern ID**: `template/orchestrator:v2.3`  
**Version**: 2.3  
**Layer**: 1  
**Inherits From**: `spl/meta-pattern:v2.3`  
**Status**: active

Core reality-agnostic orchestrator template to coordinate multiple agents to achieve goals.

YAML: `critical-patterns/orchestrator/v2.3/orchestrator.yaml`


## Overview

**Purpose**: Coordinate multiple agents toward a common goal, handling dependencies, errors, and learning from outcomes

**Context**: 
- Layer 1 core orchestrator template
- Reality-agnostic pattern
- Foundation for all orchestrator types

**Warnings**:
- Must guarantee progress if agents are available
- Must respect step dependencies
- Must preserve goal alignment in all steps
- Must handle failures gracefully with recovery strategies


## Contract

**Goal**: Coordinate multiple agents toward a common goal, handling dependencies, errors, and learning from outcomes

### Inputs

| Name | Type | Required | Description |
| --- | --- | --- | --- |
| goal_specification | object | True | Goal to be achieved with requirements and constraints |
| available_agents | array | True | Available agents with their capabilities |
| context | object | False | Optional environment context and metadata |

### Outputs

| Name | Type | Description |
| --- | --- | --- |
| execution_result | object | Results of orchestration execution |

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
