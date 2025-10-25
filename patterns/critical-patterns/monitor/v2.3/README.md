# Monitor (Core)

**Pattern ID**: `template/monitor:v2.3`  
**Version**: 2.3  
**Layer**: 1  
**Inherits From**: `spl/meta-pattern:v2.3`  
**Status**: active

Core reality-agnostic monitor template for continuous observation and feedback loops across domains.

YAML: `critical-patterns/monitor/v2.3/monitor.yaml`


## Overview

**Purpose**: Continuously observe systems, collect signals, detect anomalies, and trigger feedback actions

**Context**: 
- Layer 1 core monitor template
- Reality-agnostic pattern
- Foundation for monitoring in digital, physical, and hybrid systems

**Warnings**:
- Must be minimally invasive and avoid altering observed systems
- Sampling strategy must cover critical states
- Alerting must be precise to reduce noise


## Contract

**Goal**: Provide continuous observation and feedback with reliable alerting and minimal overhead

### Inputs

| Name | Type | Required | Description |
| --- | --- | --- | --- |
| targets | array | True | Systems or components to monitor |
| metrics | array | True | Metrics or signals to collect |
| thresholds | object | False | Alert thresholds and conditions |

### Outputs

| Name | Type | Description |
| --- | --- | --- |
| observations | array | Collected time-series observations |
| alerts | array | Alert events with severity and context |

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
