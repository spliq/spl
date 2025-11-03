# SPL's Six Layers: Architectural Overview

Version: 2.3  
Owner: SPLiQ team  
License: Apache 2.0  
Status: Public documentation  
Audience: Developers, architects, and anyone learning SPL architecture

---

## Executive Summary

SPL is organized into **six architectural layers** (L0 through L5) that are designed to create exponential intelligence through systematic composition. Each layer builds on the previous one, inheriting structure and guarantees while adding specificity. Together, these layers are designed to transform "dumb muscle" LLMs into intelligent, reliable systems.

---

## The Six Layers at a Glance

```
L5: Solutions        ─┐  Deployment
L4: Products          │  (compose patterns)
L3: Technology        │  
L2: Reality           │  Specialization
L1c: Cognitive        │  (add constraints)
L1: Critical          │  
L0: Meta-Pattern     ─┘  Foundation
```

### The Architecture

Each layer serves a specific architectural purpose:

| Layer | Name | Purpose | Inherits From | Example |
|-------|------|---------|---------------|---------|
| **L0** | Meta-Pattern | Self-describing foundation—defines what all patterns are | Itself | `meta-pattern.yaml` |
| **L1** | Critical Patterns | 13 fundamental capabilities—the "verbs" of intelligent systems | L0 | `agent`, `validator`, `translator` |
| **L1c** | Cognitive Patterns | Cognitive capabilities—reasoning, learning, decision-making | L0 | `knowledge-representation`, `ethical-reasoning` |
| **L2** | Reality Patterns | Specialization for reality type—digital, physical, hybrid | L1 or L1c | `agent/digital`, `resolver/physical` |
| **L3** | Technology Patterns | Technology-specific implementations—React, ROS, Arduino | L2 | `agent/digital/react`, `resolver/physical/path-planner` |
| **L4** | Products | Reusable product contracts—frameworks and libraries | L3 | `chatbot-framework`, `robot-controller` |
| **L5** | Solutions | Complete solutions for specific problems | implements L4 and should inherits from the same patterns as its corresponding L4 | `customer-service-bot`, `warehouse-robot` |

---

## Layer 0: Meta-Pattern

**The Self-Describing Foundation**

The Meta-Pattern is SPL's DNA—the L0 layer that defines the structure ALL patterns must follow. It's unique because it describes itself, creating a self-consistent and verifiable foundation.

### What Makes L0 Special

- **Self-describing**: The only pattern that follows its own rules
- **Foundation for all**: Every other pattern inherits from L0
- **Minimal and complete**: Contains only essential fields, nothing more
- **Enforces three pillars**: Contract, Execution, Guarantees

### Why Only One Pattern at L0?

There can be only ONE meta-pattern because:
1. Must be self-describing (cannot depend on anything else)
2. Provides foundation for all other patterns
3. Defines the three pillars architecture
4. Any additional L0 pattern would violate self-consistency

**📖 Learn More:** [What is the Meta-Pattern?](./what-is-l0-meta-pattern.md)

---

## Layer 1: Critical Patterns

**The 13 Fundamental Capabilities**

Critical Patterns are the universal building blocks—13 patterns that define what intelligent systems **do**, regardless of reality or technology.

### What Makes L1 "Critical"?

A pattern qualifies as Critical if it:
- **Cannot be decomposed** - It's atomic, not built from other patterns
- **Is reality-agnostic** - Works in digital, physical, AND hybrid realities
- **Is technology-agnostic** - Can be implemented in any suitable technology
- **Has minimal overlap** - Represents a distinct architectural role
- **Is universally needed** - Required across many systems

### The 13 Critical Patterns

The actual critical patterns in SPL v2.3 are:

**🔄 Data & Knowledge**
- `translator` - Transform data between formats
- `validator` - Verify correctness and conformance
- `entity` - Represent domain concepts and objects
- `documenter` - Generate and maintain documentation

**🤖 Intelligence & Action**
- `agent` - Autonomous goal-driven action
- `hypothesis` - Formulate and test hypotheses
- `monitor` - Observe and report on system state
- `generator` - Create new artifacts from specifications

**🛡️ Safety & Control**
- `policy-guard` - Enforce rules and policies
- `uncertainty-handler` - Manage unknowns and ambiguities
- `resolver` - Resolve conflicts and dependencies

**🌐 Infrastructure**
- `orchestrator` - Coordinate multi-pattern workflows
- `reality-bridge` - Connect digital and physical realities

**📖 Learn More:** [What are Critical Patterns?](./what-are-l1-critical-patterns.md)

---

## Layer 1c: Cognitive Patterns

**The Cognitive Capabilities**

Cognitive Patterns represent higher-order cognitive capabilities—how systems think, reason, learn, and make decisions. They complement Critical Patterns by adding intelligence.

### What Makes L1c "Cognitive"?

Cognitive Patterns:
- **Model cognitive processes** - Reasoning, learning, planning, understanding
- **Are reality-agnostic** - Like L1, work across all realities
- **Focus on cognition** - How to think, not just what to do
- **Enable intelligence** - Provide the "mind" that drives the "muscle"

### Examples of Cognitive Patterns

**🧠 Knowledge & Understanding**
- `knowledge-representation` - Organize and structure knowledge in forms that support reasoning and intelligent behavior
- `ethical-reasoning` - Moral evaluation, ethical decision-making, and value-aligned action selection

**📚 Learning & Prediction**
- `experience-acquisition` - Learn from interactions, observations, and outcomes to improve performance over time
- `expectation` - Predict future states, detect anomalies, and learn from prediction errors

**🎯 Values & Goals**
- `value-system` - Prioritization, judgment, and value-based decision making aligned with defined value hierarchies
- `motivation` - Goal pursuit, drive systems, and action selection based on internal states

**📖 Learn More:** [What are Cognitive Patterns?](./what-are-l1c-cognitive-patterns.md)

---

## Layer 2: Reality Patterns

**Specialization for Digital, Physical, and Hybrid Worlds**

Reality Patterns specialize L1/L1c patterns for specific realities—adding the constraints, interfaces, and behaviors needed for digital systems, physical devices, or hybrid environments.

### What Makes L2 "Reality-Specific"?

A pattern qualifies as Reality if it:
- **Inherits from L1 or L1c** - Specializes a Critical or Cognitive Pattern
- **Targets one reality** - Digital, physical, or hybrid
- **Adds reality constraints** - Physics, networking, sensors, latency, etc.
- **Remains technology-agnostic** - Still works with any framework/platform
- **Defines reality interface** - How the pattern interacts with its reality

### The Three Realities

**💻 Digital Reality**
- Software systems, APIs, databases, networks
- Example: `agent/digital` - Web services, chat bots, API agents
- Constraints: Network latency, data formats, authentication

**⚙️ Physical Reality**
- Hardware devices, sensors, actuators, robots
- Example: `resolver/physical` - Path planning algorithms, motion controllers
- Constraints: Physics, power, durability, calibration

**🌐 Hybrid Reality**
- Mixed digital-physical systems
- Example: `agent/hybrid` - AR assistants, smart spaces, IoT orchestrators
- Constraints: Synchronization, reality bridging, consistency

**📖 Learn More:** [What are Reality Patterns?](./what-are-l2-reality-patterns.md)

---

## Layer 3: Technology Patterns

**Technology-Specific Implementations**

Technology Patterns specialize Reality Patterns for specific technologies, frameworks, and platforms. They bridge abstract reality-aware patterns with concrete implementations.

### What Makes L3 "Technology-Specific"?

A pattern qualifies as Technology if it:
- **Inherits from L2** - Specializes a Reality Pattern
- **Requires specific technology** - React, Django, ROS, Arduino, Unity, etc.
- **Uses technology APIs** - Framework-specific interfaces and idioms
- **Provides implementation guidance** - HOW to build in this technology
- **Adds technology constraints** - Platform limitations, best practices

### Technology Pattern Specialization

Technology patterns add framework-specific implementations to reality patterns. For example:

- Digital reality patterns can be specialized for web frameworks, API technologies, or database systems
- Physical reality patterns can be specialized for robotics platforms, embedded systems, or IoT devices  
- Hybrid reality patterns can be specialized for AR/VR platforms, edge computing, or IoT-cloud bridges

**📖 Learn More:** [What are Technology Patterns?](./what-are-l3-technology-patterns.md)

---

## Layer 4: Products

**Reusable Product Contracts**

Products are L4 patterns that package multiple L3 patterns into reusable frameworks, libraries, and components. They represent "products" you can build and deploy.

### What Makes L4 a "Product"?

A pattern qualifies as Product if it:
- **Built from L3 patterns** - May combine one or more technology patterns
- **Solves product use case** - Addresses a reusable product need
- **Has clear value proposition** - What the product does and why
- **Is technology-locked** - Uses specific tech stack
- **Prepares for solutions** - Foundation for L5 deployments

### Product Pattern Composition

Products compose technology patterns into reusable frameworks, libraries, and components that can be deployed across multiple solutions. They provide standardized interfaces and proven implementations for common product needs.

**📖 Learn More:** [What are Products?](./what-are-l4-products.md)

---

## Layer 5: Solutions

**Complete Solutions for Specific Problems**

Solutions are L5 patterns that deploy L4 products to solve specific real-world problems. They are the final, deployable applications that users interact with.

### What Makes L5 a "Solution"?

A pattern qualifies as Solution if it:
- **Uses dual inheritance** - Both `implements` and `inherits_from` fields
- **Solves specific problem** - Addresses a concrete, real-world need
- **Is fully configured** - Includes deployment, data, integrations
- **Has clear customer** - Who uses this solution and why
- **Is deployable** - Ready to run in production

### Solution Pattern Deployment

Solutions are fully configured, production-ready implementations that solve specific business or operational problems. They combine products, add domain-specific configuration, and provide complete deployment artifacts.

**📖 Learn More:** [What are Solutions?](./what-are-l5-solutions.md)

---

## How the Layers Create Exponential Intelligence

### Linear vs Exponential Development

**Without SPL (Linear O(n)):**
```
GPT-3 → GPT-4 → GPT-5 → GPT-6
↑        ↑        ↑        ↑
Better   Better   Better   Still
model    model    model    hallucinates
```

**With SPL (Exponential O(2^n)):**
```
L0 (1 pattern)
  ↓
L1 (13 patterns) ─────────────→ 13× capabilities
  ↓
L2 (up to 13×3 reality types) ────→ Upper bound: 39 combinations
  ↓  (each pattern may specialize for 1-3 realities as applicable)
L3 (L2 × T technologies) ─────────→ Multiply by technology stacks
  ↓
L4 (Composed products) ───────────→ Combinatorial growth potential
  ↓
L5 (Deployed solutions) ──────────→ Unlimited possible solutions
```

### Why Exponential?

Each layer multiplies the capabilities of layers below, though the actual number depends on which patterns are applicable:

1. **L0 → L1**: Meta-pattern enables 13 critical patterns
2. **L1 → L2**: Each applicable critical pattern can specialize for 1-3 realities (digital, physical, hybrid as needed)
3. **L2 → L3**: Each reality pattern can be implemented in multiple technologies (where applicable)
4. **L3 → L4**: Products may compose multiple L3 patterns = combinatorial growth
5. **L4 → L5**: Solutions may compose multiple L4 products = exponential growth potential

**The Growth Potential:**

`Intelligence potential = L0 × (L1 patterns) × (applicable L2 realities) × (applicable L3 technologies) × (L4 compositions) × (L5 deployments)`

This represents O(2^n) growth potential—the architecture enables compound, exponential scaling as patterns compose.

---

## Layer Inheritance and Composition

### Inheritance Chain

Each layer inherits from the one above, with L5 having a unique dual inheritance model:

```
L0: Meta-Pattern (foundation)
    ↓
L1/L1c: Critical/Cognitive Patterns
    ↓
L2: Reality Patterns
    ↓
L3: Technology Patterns
    ↓
L4: Products

L5: Solutions (dual inheritance)
    ├─→ implements: L4 Product (contract - WHAT to deliver)
    └─→ inherits_from: L2/L3/L4 template (structure - HOW to implement)
```

**Note:** L5 is unique in having dual inheritance:
- `implements` field references an L4 product (defines the contract)
- `inherits_from` field references a template pattern from L2, L3, or L4 (defines the structure)
- Recommended: inherit from the same template as the L4 product for alignment

### What Gets Inherited?

When a pattern inherits from a parent layer:

✅ **Inherits:**
- Three pillars structure (contract, execution, guarantees)
- Success criteria and safety requirements
- Core capabilities and interfaces
- Truth scoring mechanisms
- Parent's constraints and requirements

➕ **Adds:**
- Layer-specific constraints (reality, technology, configuration)
- Additional capabilities and interfaces
- Specialized execution steps
- Layer-appropriate guarantees
- Composition of other patterns (at L4/L5)

---

## The Three Pillars Across All Layers

Every pattern in every layer implements the **three pillars** (contract, execution, guarantees), key structural elements that provide the foundation for SPL's architecture:

### 1. LLM Layer (The Muscle) → `contract` section
- What the pattern does (GOAL)
- What it returns (RETURN FORMAT)
- What to avoid (WARNINGS)
- What context it needs (CONTEXT)

### 2. Action Layer (Execution) → `execution` section
- How to iterate (LOOP)
- What to measure (INSPECT)
- What to produce (PRINT)

### 3. Guarantees (Ethics) → `guarantees` section
- Safety requirements (cannot violate)
- Human oversight (when to escalate)
- Success criteria (what success means)
- Compliance (regulatory/policy adherence)

**Key Point:** The three pillars ensure that at EVERY layer, patterns are:
- 🧠 **Intelligently prompted** (LLM Layer)
- ⚙️ **Properly executed** (Action Layer)
- 🛡️ **Safely guaranteed** (Guarantees)

---

## Practical Layer Selection Guide

### "Which layer should my pattern be?"

Use this decision tree:

1. **Does it define what ALL patterns are?**
   - ✅ Yes → L0 (Meta-Pattern) - There's only one!
   - ❌ No → Continue to #2

2. **Is it a fundamental capability, reality-agnostic and technology-agnostic?**
   - ✅ Yes, it's about DOING → L1 (Critical Pattern)
   - ✅ Yes, it's about THINKING → L1c (Cognitive Pattern)
   - ❌ No → Continue to #3

3. **Does it specialize for a specific reality but remain technology-agnostic?**
   - ✅ Yes → L2 (Reality Pattern)
   - ❌ No → Continue to #4

4. **Does it require a specific technology/framework?**
   - ✅ Yes, single tech implementation → L3 (Technology Pattern)
   - ❌ No → Continue to #5

5. **Does it compose multiple technology patterns into a reusable product?**
   - ✅ Yes → L4 (Product)
   - ❌ No → Continue to #6

6. **Does it deploy products to solve a specific real-world problem?**
   - ✅ Yes → L5 (Solution)
   - ❌ No → Reconsider your pattern design

---

## The Bottom Line

### What the Six Layers Give Us

🎯 **Systematic Organization**
- Clear architectural layers from foundation to solution
- Each layer has specific purpose and constraints
- No ambiguity about where patterns belong

📈 **Exponential Growth**
- O(2^n) intelligence through composition
- Each layer multiplies capabilities of layers below
- Compound growth vs. linear LLM improvement

🔒 **Inherited Guarantees**
- Three pillars enforced at every layer
- Safety and truth scores inherit upward
- Violations detected at any layer

🔄 **Composability**
- Patterns compose freely within rules
- Lower layers reused across upper layers
- Products and solutions built from verified components

🛡️ **Verifiable Intelligence**
- Truth scores at every layer
- Guarantees inherited and strengthened
- LLM muscle controlled by SPL contract

---

## Learn More About Each Layer

**Foundation:**
- 📘 [L0: Meta-Pattern](./what-is-l0-meta-pattern.md) - The self-describing foundation

**Capabilities:**
- 📗 [L1: Critical Patterns](./what-are-l1-critical-patterns.md) - 13 fundamental capabilities
- 📗 [L1c: Cognitive Patterns](./what-are-l1c-cognitive-patterns.md) - Cognitive capabilities

**Specialization:**
- 📙 [L2: Reality Patterns](./what-are-l2-reality-patterns.md) - Digital, physical, hybrid
- 📙 [L3: Technology Patterns](./what-are-l3-technology-patterns.md) - React, ROS, Arduino, etc.

**Deployment:**
- 📕 [L4: Products](./what-are-l4-products.md) - Reusable frameworks and libraries
- 📕 [L5: Solutions](./what-are-l5-solutions.md) - Complete deployable applications

**Architecture:**
- 📘 [SPL Three Pillars](../spl/spl-three-pillars.md) - LLM, Action, Guarantees architecture

---

**Version:** 2.3  
**Last Updated:** November 3, 2025  
**Status:** Public documentation
