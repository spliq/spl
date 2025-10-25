# Policy/Guard (Core)

**Pattern ID**: `template/policy-guard:v2.3`  
**Version**: 2.3  
**Layer**: 1  
**Inherits From**: `spl/meta-pattern:v2.3`  
**Status**: active

Core reality-agnostic pattern for enforcing rules, constraints, and protective boundaries.

YAML: `critical-patterns/policy-guard/v2.3/policy-guard.yaml`


## Overview

**Purpose**: Enforce rules, constraints, and protective boundaries across all systems, preventing violations and enabling controlled operation

**Context**: 
- Layer 1 core policy/guard template
- Reality-agnostic pattern
- Foundation for security, safety, and compliance systems

**Warnings**:
- Must be deterministic - same context yields same enforcement decision
- Must fail-safe - uncertain situations default to deny
- All denials must include specific violation evidence
- Guards must be composable - multiple guards can layer protection


## Contract

**Goal**: Enforce rules, constraints, and protective boundaries across all systems, preventing violations and enabling controlled operation

### Inputs

| Name | Type | Required | Description |
| --- | --- | --- | --- |
| subject | any | True | Entity, action, or operation seeking to pass the guard |
| policy | object | True | Policy definition with rules, constraints, and boundaries |
| context | object | True | Current system state, environment, and relevant metadata |
| enforcement_type | string | False | Type of enforcement: preventive, detective, or corrective |

### Outputs

| Name | Type | Description |
| --- | --- | --- |
| decision | object | Enforcement decision with action, reason, evidence, and state |

### Guarantees

- **Deterministic**: Same context always produces same enforcement decision
- **Fail-safe**: Defaults to deny when uncertain
- **Evidence-based**: All denials include specific violation evidence
- **Composable**: Multiple guards can layer protection


## Use Cases

### Digital Reality
- API access control and authentication
- Data access policies and authorization
- Security policy enforcement
- Rate limiting and quota management
- Content filtering and moderation

### Physical Reality
- Safety interlocks and emergency stops
- Motion limit switches and boundaries
- Temperature and pressure safety limits
- Hazardous material access control
- Physical security perimeter protection

### Hybrid Reality
- IoT device security policies
- Autonomous vehicle safety boundaries
- Smart building access control
- Industrial automation safety systems
- Medical device operating constraints


## Related Patterns

- **validator**: Verifies correctness and quality
- **agent**: Autonomous decision-making and action
- **orchestrator**: Coordinates multiple components
- **monitor**: Observes and detects issues
- **resolver**: Handles conflicts and errors


## Implementation Notes

Policy guards operate in three enforcement modes:
1. **Preventive**: Block violations before they occur
2. **Detective**: Detect violations as they happen
3. **Corrective**: Fix violations after detection

Guards can be layered and composed:
- Multiple guards can protect the same resource
- Guards can delegate to specialized sub-guards
- Guard decisions can be audited and reviewed

Fail modes:
- **Closed** (default): Deny access when uncertain
- **Open**: Allow access when uncertain (use cautiously)


## Examples

See `policy-guard.yaml` for complete contract and implementation examples.
