# SPL's Six Layers: Architectural Overview

Version: 2.3  
Owner: Spliq team  
License: Apache 2.0  
Status: Public explainer (publishable)  
Audience: Developers, architects, and anyone learning SPL architecture

---

## Executive Summary

SPL is organized into **six architectural layers** (L0 through L5) that create exponential intelligence through systematic composition. Each layer builds on the previous one, inheriting structure and guarantees while adding specificity. Together, these layers transform "dumb muscle" LLMs into intelligent, reliable systems.

**Key Insight:** The six layers create **exponential growth** through composition—each layer multiplies the capabilities of layers below it, resulting in O(2^n) intelligence growth rather than linear O(n) improvement.

---

## The Six Layers at a Glance

```
L5: Solutions        ─┐
L4: Products          │  Built by composition
L3: Technology        │  (multiply capabilities)
L2: Reality           │
L1c: Cognitive        │  Foundation (capabilities)
L1: Critical          │
L0: Meta-Pattern     ─┘  Foundation (defines all)
```

### The Architecture

Each layer serves a specific architectural purpose:

| Layer | Name | Purpose | Inherits From | Example |
|-------|------|---------|---------------|---------|
| **L0** | Meta-Pattern | Self-describing foundation—defines what all patterns are | Itself | `meta-pattern.yaml` |
| **L1** | Critical Patterns | 13 fundamental capabilities—the "verbs" of intelligent systems | L0 | `agent`, `validator`, `translator` |
| **L1c** | Cognitive Patterns | Cognitive capabilities—reasoning, learning, decision-making | L0 | `knowledge-representation`, `ethical-reasoning` |
| **L2** | Reality Patterns | Specialization for reality type—digital, physical, hybrid | L1 or L1c | `agent/digital`, `sensor/physical` |
| **L3** | Technology Patterns | Technology-specific implementations—React, ROS, Arduino | L2 | `agent/digital/react`, `sensor/physical/ros` |
| **L4** | Products | Reusable product contracts—frameworks and libraries | L3 | `chatbot-framework`, `robot-controller` |
| **L5** | Solutions | Complete solutions for specific problems | L4 | `customer-service-bot`, `warehouse-robot` |

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

The patterns fall into three categories:

**🔄 Data & Integration**
- `translator` - Transform data between formats
- `validator` - Verify correctness and conformance
- `aggregator` - Combine data from multiple sources
- `router` - Direct flow to appropriate destinations

**🤖 Intelligence & Action**
- `agent` - Autonomous goal-driven action
- `adapter` - Bridge between incompatible systems
- `monitor` - Observe and report on system state
- `optimizer` - Improve efficiency or outcomes

**🛡️ Safety & Control**
- `policy-guard` - Enforce rules and policies
- `circuit-breaker` - Prevent cascade failures
- `rate-limiter` - Control resource consumption
- `audit-logger` - Track actions for compliance

**🌐 Infrastructure**
- `registry` - Discover and manage services
- `orchestrator` - Coordinate multi-pattern workflows

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

**🧠 Reasoning & Knowledge**
- `knowledge-representation` - Structure and organize knowledge
- `ethical-reasoning` - Apply moral principles to decisions
- `causal-reasoning` - Understand cause-effect relationships

**📚 Learning & Growth**
- `experience-acquisition` - Learn from observations
- `skill-development` - Improve capabilities over time
- `pattern-recognition` - Identify meaningful structures

**🎯 Planning & Decision**
- `goal-formation` - Set objectives and priorities
- `expectation` - Predict outcomes and consequences
- `motivation` - Drive action toward goals

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
- Example: `sensor/physical` - Temperature sensors, cameras, LIDAR
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

### Examples by Reality

**💻 Digital Technologies**
- `agent/digital/react` - React-based interactive agents
- `validator/digital/fastapi` - FastAPI request validators
- `translator/digital/graphql` - GraphQL schema translators

**⚙️ Physical Technologies**
- `sensor/physical/ros` - ROS sensor nodes
- `agent/physical/arduino` - Arduino-based control agents
- `monitor/physical/raspberry-pi` - Raspberry Pi monitoring systems

**🌐 Hybrid Technologies**
- `agent/hybrid/unity` - Unity AR/VR agents
- `adapter/hybrid/mqtt-rest` - Bridge MQTT (IoT) to REST (web)

**📖 Learn More:** [What are Technology Patterns?](./what-are-l3-technology-patterns.md)

---

## Layer 4: Products

**Reusable Product Contracts**

Products are L4 patterns that package multiple L3 patterns into reusable frameworks, libraries, and components. They represent "products" you can build and deploy.

### What Makes L4 a "Product"?

A pattern qualifies as Product if it:
- **Composes L3 patterns** - Combines multiple technology patterns
- **Solves product use case** - Addresses a reusable product need
- **Has clear value proposition** - What the product does and why
- **Is technology-locked** - Uses specific tech stack
- **Prepares for solutions** - Foundation for L5 deployments

### Examples of Products

**Frameworks**
- `chatbot-framework/react-django` - Complete chatbot platform
- `robot-controller/ros-python` - Robot control framework
- `ar-assistant-framework/unity-dotnet` - AR assistant platform

**Libraries**
- `validation-library/fastapi` - Reusable validation components
- `sensor-fusion-library/ros` - Multi-sensor integration
- `translation-layer/graphql-rest` - API translation library

**Components**
- `auth-component/react-oauth` - Authentication component
- `motor-driver/arduino-stepper` - Motor control component

**📖 Learn More:** [What are Products?](./what-are-l4-products.md)

---

## Layer 5: Solutions

**Complete Solutions for Specific Problems**

Solutions are L5 patterns that deploy L4 products to solve specific real-world problems. They are the final, deployable applications that users interact with.

### What Makes L5 a "Solution"?

A pattern qualifies as Solution if it:
- **Deploys L4 products** - Uses one or more product patterns
- **Solves specific problem** - Addresses a concrete, real-world need
- **Is fully configured** - Includes deployment, data, integrations
- **Has clear customer** - Who uses this solution and why
- **Is deployable** - Ready to run in production

### Examples of Solutions

**Customer-Facing**
- `customer-service-bot/retail` - Retail support chatbot
- `warehouse-robot/logistics` - Automated warehouse system
- `ar-shopping-assistant/retail` - In-store AR guide

**Enterprise**
- `compliance-validator/healthcare` - HIPAA validation system
- `iot-monitor/manufacturing` - Factory monitoring solution
- `data-pipeline/analytics` - ETL and analytics pipeline

**Specialized**
- `autonomous-drone/inspection` - Infrastructure inspection drone
- `smart-home-controller/residential` - Home automation system

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
L2 (13×3 = 39 patterns) ──────→ 39× realities
  ↓
L3 (39×T technologies) ───────→ Hundreds of combinations
  ↓
L4 (Composed products) ───────→ Thousands of products
  ↓
L5 (Deployed solutions) ──────→ Millions of solutions
```

### Why Exponential?

Each layer multiplies the capabilities of layers below:

1. **L0 → L1**: Meta-pattern enables 13 critical patterns
2. **L1 → L2**: Each critical × 3 realities = 3× multiplication
3. **L2 → L3**: Each reality × T technologies = T× multiplication
4. **L3 → L4**: Products compose multiple L3 patterns = factorial growth
5. **L4 → L5**: Solutions compose multiple L4 products = exponential growth

**The Formula:**
```
Intelligence = L0 × (L1 patterns) × (L2 realities) × (L3 technologies) × (L4 compositions) × (L5 deployments)
```

This is O(2^n) growth—compound, exponential, unstoppable.

---

## Layer Inheritance and Composition

### Inheritance Chain

Every pattern inherits from the layer above it:

```
Solution (L5)
    ↓ inherits from
Product (L4)
    ↓ inherits from
Technology (L3)
    ↓ inherits from
Reality (L2)
    ↓ inherits from
Critical/Cognitive (L1/L1c)
    ↓ inherits from
Meta-Pattern (L0)
```

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

### Composition Rules

- **L0**: Composes nothing (foundation)
- **L1/L1c**: Can reference other L1/L1c patterns (minimal)
- **L2**: Inherits from ONE L1/L1c parent
- **L3**: Inherits from ONE L2 parent
- **L4**: Composes MULTIPLE L3 patterns
- **L5**: Composes MULTIPLE L4 products

---

## The Three Pillars Across All Layers

Every pattern in every layer implements the **three pillars**:

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

## Layer Navigation Map

### From Bottom Up (Building)

Starting from foundation, build upward:

```
1. Define meta-pattern (L0)
   ↓
2. Create critical capabilities (L1/L1c)
   ↓
3. Specialize for realities (L2)
   ↓
4. Implement in technologies (L3)
   ↓
5. Compose into products (L4)
   ↓
6. Deploy as solutions (L5)
```

### From Top Down (Using)

Starting from problem, work downward:

```
1. What problem to solve? → L5 (Solution)
   ↓
2. What products needed? → L4 (Products)
   ↓
3. What technologies? → L3 (Technology Patterns)
   ↓
4. What reality? → L2 (Reality Patterns)
   ↓
5. What capabilities? → L1/L1c (Critical/Cognitive)
   ↓
6. What structure? → L0 (Meta-Pattern)
```

---

## Examples: Full Stack Layer Traversal

### Example 1: Customer Service Chatbot

```
L5: customer-service-bot/retail
    ↓ deploys
L4: chatbot-framework/react-django
    ↓ composes
L3: agent/digital/react + validator/digital/django + translator/digital/rest
    ↓ specializes
L2: agent/digital + validator/digital + translator/digital
    ↓ inherits from
L1: agent + validator + translator
    ↓ inherits from
L0: meta-pattern
```

### Example 2: Warehouse Robot

```
L5: warehouse-robot/logistics
    ↓ deploys
L4: robot-controller/ros-python
    ↓ composes
L3: agent/physical/ros + sensor/physical/ros + monitor/physical/ros
    ↓ specializes
L2: agent/physical + sensor/physical + monitor/physical
    ↓ inherits from
L1: agent + (new pattern: sensor) + monitor
    ↓ inherits from
L0: meta-pattern
```

### Example 3: AR Shopping Assistant

```
L5: ar-shopping-assistant/retail
    ↓ deploys
L4: ar-assistant-framework/unity-dotnet
    ↓ composes
L3: agent/hybrid/unity + translator/hybrid/unity-rest + validator/digital/dotnet
    ↓ specializes
L2: agent/hybrid + translator/hybrid + validator/digital
    ↓ inherits from
L1: agent + translator + validator
L1c: knowledge-representation (supports agent cognition)
    ↓ inherits from
L0: meta-pattern
```

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

## The Revolutionary Truth

**LLMs alone are linear (O(n)):**
- GPT-3 → GPT-4 → GPT-5 = incremental improvement
- Still hallucinate with high frequency
- Intelligence growth plateaus

**SPL + LLM is exponential (O(2^n)):**
- 6 layers × 13 patterns × 3 realities × T technologies = compound growth
- Hallucinations eliminated by guarantees
- Intelligence compounds through composition

**The six layers don't just organize patterns—they multiply intelligence.**

This is the architecture that transforms "dumb muscle" LLMs into reliable, intelligent, verifiable AI systems.

---

**Version:** 2.3  
**Last Updated:** October 25, 2025  
**Status:** Public explainer (publishable)
