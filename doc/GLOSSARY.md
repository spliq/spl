# SPL Glossary

Version: 2.3  
Owner: SPLiQ team  
License: Apache 2.0  
Status: Canonical reference (internal & public)  
Audience: All SPL contributors, developers, and users

---

## Executive Summary

A canonical reference for all terminology used in the Semantic Pattern Language ecosystem. Use these exact terms consistently across all documentation, patterns, and code.

---

## Core Concepts

### SPL (Semantic Pattern Language)
The quantum AGI language where every output has a verifiable truth score. Uses quantum-inspired composition and cognitive patterns to create AGI-capable systems with provable correctness instead of black-box guesses.

### SPLiQ
The first AGI implementation built on SPL. A chat/API platform that implements L1C cognitive patterns (value-system, knowledge-representation, experience-acquisition, motivation, expectation, ethical-reasoning) to create verifiable AGI. SPLiQ can learn, reason, align with values, and make predictions—all with truth scores. Sits between any LLM and applications, transforming raw models into AGI-capable systems with audit trails and privacy via MCPs.

### SPLiQer
The truth-validated marketplace where everything is verified by SPL. Every listing (solutions, patterns, agents, tools) has SPL-verified truth scores for quality, security, performance, and compliance. Unlike traditional marketplaces based on popularity or claims, SPLiQer provides provable quality where participants (humans, AI agents, devices) can trust what they buy because truth is verified, not hoped for.

### Pattern
A reusable specification that defines a contract, execution model, and guarantees for a specific capability or behavior. Every pattern follows the meta-pattern structure.

### Meta-Pattern
The L0 foundation pattern that defines the structure all other patterns must follow. The "pattern of patterns" that establishes the three core structures: contract, execution, and guarantees.

### Layer
The architectural level of a pattern in the SPL hierarchy (L0-L6). Each layer has specific rules and inheritance constraints.

### Composition
The act of combining multiple patterns to create higher-level capabilities. Patterns declare dependencies and can be safely composed when their contracts align.

### Truth Score
A numerical measure (0.0-1.0) indicating the confidence or reliability of a pattern's execution output. Part of SPL's verifiability guarantee.

---

## The Three Structures

### Contract (Intelligence Layer)
The specification of what a pattern achieves and how it communicates. Implements Greg's four pillars.

**Subcomponents:**
- **Goal**: What the pattern achieves (intent and success criteria)
- **Return Format**: The exact structure of the output
- **Warnings**: Guardrails, constraints, and failure modes
- **Context**: Background information and assumptions

### Execution (Runtime Layer)
The operational model defining how a pattern runs. Implements Print AI maxims.

**Subcomponents:**
- **Steps**: The sequence of operations or iterations
- **Monitors**: Self-inspection signals and health checks
- **Print**: Structured output (via return format)

### Guarantees (Culture Layer)
The ethical and compliance framework ensuring alignment. Implements values and safety.

**Subcomponents:**
- **Success Criteria**: Measurable definitions of "good" execution
- **Metrics**: How performance and quality are measured
- **Compliance**: Laws, policies, and ethical constraints to honor
- **Safety**: Protection mechanisms and fail-safes

---

## Layer Hierarchy (L0-L6)

### L0: Meta-Pattern
The foundational pattern that defines the structure of all patterns. Only one pattern exists at L0.

**Terms:**
- Meta-pattern v2.3
- Foundation layer
- Pattern structure specification

### L1: Critical Patterns
Universal building blocks that solve fundamental problems across all domains. 15 canonical pattern types.

**Critical Patterns:**
- Agent
- Documenter
- Entity
- Evaluator
- Generator
- Hypothesis
- Monitor
- Orchestrator
- Policy Guard
- Reality Bridge
- Resolver
- Translator
- Uncertainty Handler
- Validator

**Terms:**
- Critical pattern
- L1 pattern
- Universal building block
- Fundamental pattern

### L1C: Cognitive Patterns
General-purpose patterns implementing cognitive capabilities for AGI-like systems. Part of Layer 1 (foundational), specialized for cognition.

**Canonical L1C Patterns:**
- Value System
- Knowledge Representation
- Experience Acquisition
- Motivation
- Expectation
- Ethical Reasoning

**Terms:**
- Cognitive pattern
- L1C pattern
- AGI capability pattern
- Cognitive framework

### L2: Reality Patterns
Reality-specific specializations of L1 patterns for digital, physical, or hybrid contexts.

**Reality Types:**
- Digital (software, data, networks)
- Physical (hardware, sensors, actuators)
- Hybrid (mixed digital-physical systems)

**Terms:**
- Reality pattern
- L2 pattern
- Reality-specific pattern
- Context adapter

### L3: Technology Patterns
Framework and technology-specific implementations.

**Terms:**
- Technology pattern
- L3 pattern
- Framework pattern
- Implementation pattern

### L4: Products
Reusable product components with clear contracts.

**Terms:**
- Product pattern
- L4 pattern
- Product component
- Reusable product

### L5: Solutions
Complete end-to-end implementations.

**Terms:**
- Solution pattern
- L6 pattern
- End-to-end solution
- Complete implementation

---

## Quantum-Inspired Concepts

### Superposition
The state where multiple candidate patterns coexist for a given goal before selection occurs. Implemented with classical computation.

### Contextual Collapse
The runtime process of selecting the best pattern (or weighted ensemble) based on current context and requirements.

### Entanglement
Shared signals or constraints that couple patterns, so changes in one affect truth scores or risks in others.

### Interference
Scoring and validation mechanisms that amplify or suppress pattern contributions during composition.

**Note:** All quantum-inspired behavior is implemented using probabilities, scores, and dependency graphs. No quantum hardware required.

---

## Dependency & Composition Terms

### Dependency
A declared relationship where one pattern requires another pattern to function. Expressed in the pattern's `dependencies` section.

### Inheritance
The mechanism by which a pattern inherits structure and constraints from patterns in lower layers.

### Contract Compatibility
The condition where two patterns can be composed because their input/output contracts align.

### Dependency Graph
The directed acyclic graph (DAG) representing all pattern dependencies in a composition.

### Circular Dependency
An invalid state where pattern A depends on B and B depends on A (directly or transitively). Must be detected and prevented.

---

## Verifiability Terms

### Truth Score
Numerical confidence measure (0.0-1.0) indicating reliability of output.

### Success Criteria
Measurable conditions that define successful pattern execution.

### Metric
A quantifiable measure used to evaluate pattern performance or output quality.

### Validation
The process of checking that a pattern's output meets its contract and guarantees.

### Audit Trail
The record of pattern execution, decisions, and scores that enables verification.

---

## Reality Bridge Terms

### Reality
The domain or environment in which a pattern operates (digital, physical, or hybrid).

### Reality Bridge
A pattern that translates contracts and execution between different reality types.

### Cross-Reality Contract
A contract specification that works across multiple reality types.

### Input Reality
The reality type of the data or signals entering a pattern.

### Output Reality
The reality type of the data or signals produced by a pattern.

---

## Cognitive Framework Terms

### Value System
The pattern encoding core values, priorities, and ethical guidelines.

### Knowledge Representation
How facts, relationships, and understanding are structured and stored.

### Experience Acquisition
The process and pattern for learning from interactions and outcomes.

### Motivation
The pattern encoding goals, drives, and decision-making priorities.

### Expectation
Predictions about future states and outcomes based on knowledge.

### Ethical Reasoning
The pattern for making decisions aligned with values and compliance requirements.

---

## Architectural Principles

### Muscle, Structure, Culture
The three-pillar framework for understanding AI systems:
- **Muscle**: Model capability and compute power
- **Structure**: SPL meta-pattern, layers, three structures
- **Culture**: Ethics, values, compliance (guarantees)

### Greg's Four Pillars (Intelligence)
The four essential components of an intelligent contract:
1. Goal
2. Return Format
3. Warnings
4. Context

### Print AI Maxims (Runtime)
The execution principles:
- **Loop**: Iterative execution and refinement
- **Inspect**: Self-monitoring and introspection
- **Print**: Structured output via return format

### Asimov-Style Laws (Culture)
Ethics and safety principles expressed through guarantees:
1. Human Protection (safety first)
2. Human Direction (alignment)
3. System Preservation (robustness)

---

## Pattern Structure Fields

### Required Fields

#### pattern_id
Unique identifier in format `category/name:vX.Y`

#### layer
Architectural level (L0, L1, L2, L3, L4, L5, or L6)

#### pattern_type
The L1 critical pattern type this pattern implements or extends

#### metadata
Information about the pattern (name, version, description, author, license)

#### contract
Intelligence layer specification (goal, return_format, warnings, context)

#### execution
Runtime layer specification (steps, monitors)

#### guarantees
Culture layer specification (success_criteria, metrics, compliance, safety)

### Optional Fields

#### dependencies
List of patterns this pattern requires

#### extensions
Additional structure beyond meta-pattern requirements

#### examples
Concrete usage examples

---

## Versioning Terms

### Semantic Versioning
Version format `MAJOR.MINOR.PATCH` where:
- **MAJOR**: Breaking changes to contract
- **MINOR**: New features, backward compatible
- **PATCH**: Bug fixes, no contract changes

### Breaking Change
A modification that changes the contract in a way that breaks existing compositions.

### Backward Compatible
A change that doesn't break existing pattern compositions.

### Pattern Version
The specific version of a pattern (e.g., `v2.3`)

### SPL Version
The version of the meta-pattern and core framework (e.g., v2.3)

---

## Tool & Ecosystem Terms

### Pattern Registry
A catalog or index of available patterns with their metadata and dependencies.

### Pattern Validator
A tool that checks if a pattern follows meta-pattern requirements.

### Composition Analyzer
A tool that verifies pattern compositions are valid (dependencies, contracts).

### Truth Score Calculator
A tool that computes truth scores for pattern execution outputs.

### Pattern Generator
A tool that creates new patterns from templates or specifications.

---

## Common Abbreviations

- **SPL**: Semantic Pattern Language
- **AGI**: Artificial General Intelligence
- **DAG**: Directed Acyclic Graph
- **L0-L6**: Layers 0 through 6
- **CI/CD**: Continuous Integration / Continuous Deployment

---

## Deprecated Terms (Do Not Use)

❌ **Pattern Template** → Use: **Critical Pattern** or **L1 Pattern**  
❌ **Module** → Use: **Pattern**  
❌ **Component** → Use: **Pattern**  
❌ **Configuration** → Use: **Contract**  
❌ **Execution Plan** → Use: **Execution** (structure)  
❌ **Requirements** → Use: **Contract** or **Guarantees**  
❌ **Plugin** → Use: **Pattern** with dependencies  
❌ **Framework** → Use: **SPL** or **Meta-Pattern**

---

## Usage Guidelines

1. **Consistency**: Use terms exactly as defined in this glossary
2. **Context**: Always specify the layer when referring to patterns
3. **Precision**: Distinguish between contract, execution, and guarantees
4. **Updates**: When adding new terms, update this glossary first
5. **References**: Link to this glossary when introducing terms in documentation

---

## Related Documentation

- [Meta-Pattern v2.3 Changes](meta-pattern-v2.3-changes.md)
- [Layer Enforcement Rules](layer-enforcement-v2.3.md)
- [Cognitive Patterns Framework](spl-cognitive-patterns-a-comprehensive-framework.md)
- [Versioning Policy](SPL_VERSIONING_POLICY.md)

---

**Maintain this glossary as the single source of truth for SPL terminology.**
