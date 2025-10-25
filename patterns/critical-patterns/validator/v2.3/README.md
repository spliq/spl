# Validator (Core)

**Pattern ID**: `template/validator:v2.3`  
**Version**: 2.3  
**Layer**: 1  
**Inherits From**: `spl/meta-pattern:v2.3`  
**Status**: active

Core reality-agnostic validator template for verifying conformance.

YAML: `critical-patterns/validator/v2.3/validator.yaml`


## Overview

**Purpose**: Objectively verify correctness, compliance, and integrity of artifacts against defined rules

**Context**: 
- Layer 1 core validator template - reality agnostic, enables specialization at L2+ for digital, physical, hybrid domains

**Warnings**:
- Must be deterministic - same input yields same result
- Must not modify subject under validation
- All failures must include specific evidence


## Contract

**Goal**: Objectively verify correctness, compliance, and integrity of artifacts against defined rules

### Inputs

| Name | Type | Required | Description |
| --- | --- | --- | --- |
| subject | any | True | Artifact under validation (file, config, structure, measurement) |
| criteria | any | True | Schema/rules/invariants or reference suite defining valid state |
| validation_type | string | False | - objective: Ground truth exists, deterministic validation
- subjective: No ground truth, validation based on consistency/coherence
- consensus: Validation by agreement among multiple validators
 |
| consensus_parameters | object | False | Parameters for consensus-based validation |
| context | object | False | Optional environment, platform info, tolerances for validation |

### Outputs

| Name | Type | Description |
| --- | --- | --- |
| result | string | Binary validation outcome |
| evidence | array | List of findings with locations, severity, and messages |
| metrics | object | Counts, coverage percentages, timing measurements |
| version | string | Validator version and criteria version |

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
