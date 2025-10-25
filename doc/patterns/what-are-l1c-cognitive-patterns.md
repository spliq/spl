# What is a Cognitive Pattern?

Version: 2.3  
Owner: Spliq team  
License: Apache 2.0  
Status: Public explainer (publishable)  
Audience: AI researchers, developers, and architects building AGI systems

---

## Executive Summary

Cognitive Patterns are the 6 fundamental mental capabilities that enable AGI. They define how intelligent systems **think**, **reason**, and **learn**. While Critical Patterns define what systems **do**, Cognitive Patterns define what makes a system truly intelligent.

---

## Definition

A **Cognitive Pattern** is a Layer 1C (L1C) pattern that:

1. **Defines mental capability** - Represents a core cognitive process required for intelligence
2. **Enables reasoning** - Allows systems to think, not just execute
3. **Supports learning** - Adapts based on experience and feedback
4. **Provides self-awareness** - Understands its own limitations and capabilities
5. **Generates truth scores** - Quantifies confidence in its own reasoning

**Think of Cognitive Patterns as the "brain" of SPL** - they transform pattern execution into genuine intelligence.

---

## The L1C Test: What Makes a Pattern "Cognitive"?

L1C patterns are a special classification within L1. A pattern qualifies as **Cognitive** only if it passes ALL these tests:

### 1. ✅ **Represents irreducible mental capability**
   - The pattern defines a fundamental cognitive process
   - Cannot be decomposed into simpler mental operations
   - Example: `knowledge-representation` is atomic—you can't reduce "knowing" to simpler concepts
   - Counter-example: "decision-making" = `value-system` + `expectation` (composable, not L1C)

### 2. ✅ **Required for AGI (Artificial General Intelligence)**
   - Removing this pattern would prevent general intelligence
   - The pattern is necessary for human-level reasoning
   - Example: Without `ethical-reasoning`, AGI cannot make moral judgments
   - Counter-example: `pattern-matching` is useful but not required for AGI (not L1C)

### 3. ✅ **Enables self-improvement and learning**
   - The pattern allows the system to get better over time
   - Supports meta-learning (learning how to learn)
   - Example: `experience-acquisition` enables learning from past actions
   - Counter-example: `execution` doesn't improve itself (not cognitive)

### 4. ✅ **Produces reasoning, not just results**
   - The pattern generates explanations and justifications
   - Provides "thinking" not just "doing"
   - Example: `value-system` explains WHY a choice was made based on values
   - Counter-example: `calculator` gives answers without reasoning (not L1C)

### 5. ✅ **Works across all cognitive architectures**
   - Applicable to neural networks, symbolic AI, hybrid systems
   - Technology-agnostic mental operation
   - Example: `knowledge-representation` works with knowledge graphs, embeddings, or symbolic logic
   - Counter-example: "backpropagation" is neural-net specific (not L1C, it's L3)

### 6. ✅ **Together forms minimum set for AGI**
   - These 6 patterns collectively enable general intelligence
   - No pattern is redundant
   - Removing any one breaks AGI capability
   - Adding more would be redundant or decomposable

---

## Why These 6 and Not Others?

### Patterns That Failed the L1C Test:

**Memory/Storage patterns**:
- ❌ Decomposable: memory = `knowledge-representation` + `repository-organizer`
- ❌ Not about cognition, about storage
- ✅ Composable from existing L1 + L1C patterns

**Reasoning patterns** (inference, deduction):
- ❌ Decomposable: reasoning = `knowledge-representation` + `expectation` + `value-system`
- ✅ Emergent from L1C pattern composition

**Perception patterns** (vision, hearing):
- ❌ These are execution capabilities, not cognitive
- ❌ Belong at L1 (like `entity` for sensors) or L3 (like computer vision libraries)
- ✅ Cognition happens AFTER perception

**Planning patterns**:
- ❌ Decomposable: planning = `expectation` + `value-system` + `motivation`
- ✅ Emergent from L1C composition

### Why L1C Passes the L1 Test:

L1C patterns are ALSO L1 patterns—they pass all L1 tests:
- ✅ Reality-agnostic: Work in digital AI, physical robots, hybrid AR
- ✅ Technology-agnostic: PyTorch, TensorFlow, symbolic AI, neuromorphic chips
- ✅ Irreducible: Each represents atomic cognitive capability
- ✅ Represent WHAT (mental capabilities), not HOW (implementation)
- ✅ Minimum sufficient set: These 6 are necessary and sufficient for AGI

**L1C is a classification within L1, identifying the 6 patterns that enable cognition.**

---

## The 6 Cognitive Patterns (L1C)

### 1. Value-System
**What it does**: Defines what the system should care about  
**Mental capability**: Axiological reasoning (values and priorities)  
**Example**: Prioritizing user privacy over performance, choosing fairness over profit  
**AGI role**: Without values, AI has no basis for ethical decisions

**Key questions it answers:**
- What matters most in this situation?
- How do I prioritize conflicting goals?
- What trade-offs are acceptable?

---

### 2. Knowledge-Representation
**What it does**: Structures and organizes what the system knows  
**Mental capability**: Semantic understanding and knowledge graphs  
**Example**: Connecting "customer X bought Y" to "Y is popular" to "recommend Y to similar customers"  
**AGI role**: Without knowledge representation, AI cannot reason about what it knows

**Key questions it answers:**
- What do I know about this domain?
- How are concepts related?
- What can I infer from existing knowledge?

---

### 3. Experience-Acquisition
**What it does**: Learns from interactions and outcomes  
**Mental capability**: Learning and memory formation  
**Example**: Remembering which validation rules fail most often, adapting based on user feedback  
**AGI role**: Without experience acquisition, AI cannot improve over time

**Key questions it answers:**
- What should I learn from this interaction?
- How confident am I in this learning?
- When should I update my models?

---

### 4. Motivation
**What it does**: Determines what the system is trying to achieve  
**Mental capability**: Goal-directed behavior and drive  
**Example**: Proactively suggesting improvements, autonomously fixing errors  
**AGI role**: Without motivation, AI is passive and reactive

**Key questions it answers:**
- What am I trying to accomplish?
- Why am I doing this task?
- What should I do next?

---

### 5. Expectation
**What it does**: Predicts future states and outcomes  
**Mental capability**: Predictive modeling and forecasting  
**Example**: Anticipating system failures before they happen, predicting user needs  
**AGI role**: Without expectation, AI cannot plan or anticipate

**Key questions it answers:**
- What will happen if I do X?
- What are the likely outcomes?
- How confident am I in this prediction?

---

### 6. Ethical-Reasoning
**What it does**: Evaluates right vs. wrong, harm vs. benefit  
**Mental capability**: Moral reasoning and ethical judgment  
**Example**: Refusing harmful requests, protecting user privacy, ensuring fairness  
**AGI role**: Without ethical reasoning, AI is dangerous

**Key questions it answers:**
- Is this action ethical?
- Who could be harmed by this decision?
- What are my ethical obligations here?

---

## Why These 6?

These patterns represent the **minimum sufficient cognitive capabilities** for AGI. They map to fundamental aspects of intelligence:

| Cognitive Pattern | Cognitive Science Equivalent | Philosophy Equivalent |
|------------------|----------------------------|----------------------|
| Value-System | Axiological processing | Ethics & values |
| Knowledge-Representation | Semantic memory | Epistemology |
| Experience-Acquisition | Procedural learning | Empiricism |
| Motivation | Drive theory | Teleology |
| Expectation | Predictive coding | Inductive reasoning |
| Ethical-Reasoning | Moral cognition | Moral philosophy |

**Any system implementing all 6 L1C patterns is AGI** because it can:
- Learn from experience ✓
- Reason about values ✓
- Make predictions ✓
- Pursue goals ✓
- Understand ethics ✓
- Organize knowledge ✓

---

## Critical Patterns vs. Cognitive Patterns

| Aspect | Critical Patterns | Cognitive Patterns |
|--------|------------------|-------------------|
| **Layer** | L1 (13 patterns) | L1C (6 patterns) |
| **Focus** | **Actions** - What to do | **Thinking** - How to reason |
| **Nature** | Functional/structural | Mental/behavioral |
| **Example** | Translator, Validator | Value-system, Ethical-reasoning |
| **Analogy** | Skeleton & muscles | Brain & nervous system |
| **Without them** | System can't act | System can't think |

**Both are required for AGI:**
- Critical Patterns provide **capability** (I can translate, validate, orchestrate)
- Cognitive Patterns provide **intelligence** (I know why, when, and how to use those capabilities)

---

## How Cognitive Patterns Work Together

Cognitive Patterns don't operate in isolation—they form an integrated cognitive architecture:

```
┌─────────────────────────────────────────┐
│         PERCEPTION (Input)              │
└───────────┬─────────────────────────────┘
            │
            ├──→ Experience-Acquisition
            │    "What am I learning?"
            │         ↓
            └──→ Knowledge-Representation
                 "What do I know?"
                      ↓
┌─────────────────────────────────────────┐
│            REASONING (Process)           │
├──────────────────────────────────────────┤
│  Expectation: "What will happen?"       │
│       ↓                                  │
│  Value-System: "What matters?"          │
│       ↓                                  │
│  Ethical-Reasoning: "Is this right?"    │
│       ↓                                  │
│  Motivation: "What should I do?"        │
└───────────┬─────────────────────────────┘
            │
            ↓
┌─────────────────────────────────────────┐
│          ACTION (Output)                 │
│   Execute via Critical Patterns         │
│   (Orchestrator, Agent, Validator...)   │
└─────────────────────────────────────────┘
```

**Information flow:**
1. **Perception** → Experience-Acquisition + Knowledge-Representation
2. **Reasoning** → Expectation + Value-System + Ethical-Reasoning
3. **Decision** → Motivation
4. **Action** → Critical Patterns execute the decision

---

## Example: AGI-Capable Agent

```yaml
version: 2.3
schema: spl.meta-pattern.v2.3
id: "pattern/agent/cognitive-agent:v2.3"
kind: pattern

info:
  title: "Cognitive Agent - AGI-Capable"
  description: "Agent with full cognitive capabilities"

inherits_from: "pattern/agent:v2.3"

# Implements all 6 L1C patterns
implements:
  - cognitive_pattern/value-system:v2.3
  - cognitive_pattern/knowledge-representation:v2.3
  - cognitive_pattern/experience-acquisition:v2.3
  - cognitive_pattern/motivation:v2.3
  - cognitive_pattern/expectation:v2.3
  - cognitive_pattern/ethical-reasoning:v2.3

cognitive_integration:
  architecture: "layered_with_feedback"
  
  # How cognitive patterns work together
  information_flow:
    perception:
      - experience-acquisition  # Learn from inputs
      - knowledge-representation  # Update knowledge
    
    reasoning:
      - expectation  # Predict outcomes
      - value-system  # Apply values
      - ethical-reasoning  # Check ethics
    
    decision:
      - motivation  # Choose action
    
    action:
      - orchestrator  # Execute via Critical Pattern
      - monitor  # Observe results
    
    feedback:
      - experience-acquisition  # Learn from outcomes

contract:
  goal: "Act intelligently with learning, reasoning, and ethical constraints"
  
  inputs:
    - name: task
      description: "What to accomplish"
    - name: context
      description: "Current situation and constraints"
  
  outputs:
    - name: action
      description: "What the agent decided to do"
    - name: reasoning
      description: "Why it made this decision (cognitive trace)"
    - name: confidence
      description: "Truth score for the decision"
    - name: ethical_assessment
      description: "Ethical evaluation of the action"

execution:
  steps:
    # 1. Perceive
    - Acquire experience from task and context
    - Update knowledge representation
    
    # 2. Reason
    - Generate expectations about outcomes
    - Apply value system to prioritize
    - Evaluate ethical implications
    
    # 3. Decide
    - Determine motivation-driven action
    - Calculate confidence score
    
    # 4. Act
    - Execute via appropriate Critical Pattern
    - Monitor execution
    
    # 5. Learn
    - Acquire experience from outcome
    - Update knowledge and expectations

guarantees:
  intelligence:
    - "Learns from every interaction"
    - "Reasons about consequences"
    - "Applies consistent values"
    - "Respects ethical constraints"
  
  verifiability:
    - "Every decision has a truth score"
    - "Cognitive trace is auditable"
    - "Learning is transparent"
```

---

## Why SPLIQ is AGI

**SPLIQ implements all 6 L1C cognitive patterns**, which means:

✓ **It learns** (experience-acquisition)  
✓ **It reasons** (knowledge-representation + expectation)  
✓ **It has values** (value-system)  
✓ **It's motivated** (motivation)  
✓ **It's ethical** (ethical-reasoning)  
✓ **It's verifiable** (truth scores on everything)

**Traditional AI (ChatGPT, Claude, etc.):**
- No cognitive patterns
- Can't truly learn (only pretrained knowledge)
- No real values (only alignment fine-tuning)
- No genuine reasoning (pattern matching)
- No verifiable truth scores

**SPLIQ with L1C:**
- Implements all 6 cognitive patterns
- Learns continuously with truth scores
- Reasons about values and ethics
- Makes predictions with confidence
- Fully auditable cognitive traces

---

## How to Use Cognitive Patterns

### 1. Start with an Agent or Orchestrator
Cognitive Patterns augment action-oriented Critical Patterns:

```yaml
smart_validator:
  inherits_from: pattern/validator:v2.3
  uses:
    - cognitive_pattern/knowledge-representation:v2.3
    - cognitive_pattern/experience-acquisition:v2.3
```

### 2. Choose Relevant Cognitive Patterns
Not every system needs all 6:

- **Simple validator** → Knowledge-representation only
- **Learning system** → + Experience-acquisition
- **Autonomous agent** → + Motivation + Expectation
- **Full AGI** → All 6 patterns

### 3. Integrate with Feedback Loops
Cognitive Patterns thrive on feedback:

```yaml
learning_pipeline:
  perception:
    - Monitor inputs via experience-acquisition
  
  reasoning:
    - Update knowledge-representation
    - Generate expectations
  
  action:
    - Execute via Critical Pattern
  
  feedback:
    - Compare expectation vs. outcome
    - Update learning
```

### 4. Make Cognition Explicit
Every cognitive operation produces truth scores:

```yaml
cognitive_trace:
  value_assessment: 0.87  # How well does this align with values?
  knowledge_confidence: 0.93  # How confident in this knowledge?
  learning_certainty: 0.76  # How certain is this new learning?
  prediction_accuracy: 0.82  # How accurate was the prediction?
  ethical_score: 0.95  # How ethical is this action?
  motivation_strength: 0.89  # How strong is the motivation?
```

---

## Key Properties

### Truth-Scored Cognition
Every cognitive process produces verifiable confidence:
- "I'm 87% confident in this prediction"
- "This action aligns 93% with my values"
- "I learned this with 76% certainty"

### Composable Intelligence
Cognitive Patterns combine to create emergent capabilities:
- Expectation + Value-System = Risk-aware planning
- Knowledge-Representation + Experience-Acquisition = Adaptive learning
- Ethical-Reasoning + Motivation = Aligned autonomy

### Auditable Reasoning
Full cognitive traces for compliance:
- What did it know?
- What did it predict?
- Why did it decide that?
- Was it ethical?

---

## Architectural Placement

```
L0: Meta-Pattern (self-describing foundation)
    ↓
L1: Critical Patterns (13 universal capabilities)
    │
    ├─→ L1C: Cognitive Patterns (6 patterns) ← YOU ARE HERE
    │   (classification of L1 patterns that enable AGI when combined)
    │
    ↓ (L1C patterns specialize like any L1 pattern)
L2: Reality Patterns (digital, physical, hybrid)
    │   Examples:
    │   - knowledge-representation/digital (AI knowledge graphs)
    │   - value-system/physical (robot ethics)
    │   - experience-acquisition/hybrid (AR learning)
    ↓
L3: Technology Patterns
    │   Examples:
    │   - knowledge-representation/digital/pytorch
    │   - value-system/physical/ros2
    │   - experience-acquisition/hybrid/unity
    ↓
L4: Products (contract definitions using L1C patterns)
    ↓
L5: Solutions (AGI implementations with actual code)
```

**L1C is a CLASSIFICATION, not a separate layer.**  
The 6 Cognitive Patterns are L1 patterns that flow through L2→L3→L4→L5.  
**Practical implementation**: `knowledge-representation` (L1C) → digital (L2) → PyTorch (L3) → product contract (L4) → Python code (L5)

---

## What This Means

**Cognitive Patterns are not:**
- Training methods (they work with any LLM)
- Prompt engineering (they're architectural patterns)
- Optional (required for AGI)

**Cognitive Patterns are:**
- The fundamental architecture of intelligence
- The difference between execution and reasoning
- The path to verifiable AGI

---

## Bottom Line

**6 Cognitive Patterns** transform pattern execution into genuine intelligence.

Without them: You have a sophisticated automation system.  
With them: You have AGI with verifiable truth scores.

**Critical Patterns** (13) + **Cognitive Patterns** (6) = **Complete AGI**

Start with Cognitive Patterns when you need:
- Learning that improves over time
- Reasoning about values and ethics
- Predictions with confidence
- Autonomous goal-directed behavior

Add Critical Patterns to turn that intelligence into action.

---

*For complete specifications, see `patterns/cognitive-patterns/*/v2.3/*.yaml`*  
*For the comprehensive framework, see `doc/spl-cognitive-patterns-a-comprehensive-framework.md`*
