# Hypothesis (Core)

**Pattern ID**: `template/hypothesis:v2.3`  
**Version**: 2.3  
**Layer**: 1  
**Inherits From**: `spl/meta-pattern:v2.3`  
**Status**: active

Core reality-agnostic hypothesis template to formulate, test, and refine propositions about the world.

YAML: `critical-patterns/hypothesis/v2.3/hypothesis.yaml`


## Overview

**Purpose**: Formulate testable propositions, design experiments, evaluate evidence, and refine understanding

**Context**: 
- Layer 1 core hypothesis template
- Reality-agnostic pattern
- Foundation for scientific reasoning and AGI

**Warnings**:
- Must be falsifiable
- Must design controlled experiments
- Must be evidence-based
- Must document assumptions


## Contract

**Goal**: Formulate testable propositions, design experiments, evaluate evidence, and refine understanding

### Inputs

| Name | Type | Required | Description |
| --- | --- | --- | --- |
| observation | object | True | Initial observation or phenomenon to explain |
| prior_knowledge | object | False | Existing knowledge and theories |
| constraints | object | False | Experimental constraints and resources |

### Outputs

| Name | Type | Description |
| --- | --- | --- |
| hypothesis_result | object | Hypothesis evaluation results |

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
