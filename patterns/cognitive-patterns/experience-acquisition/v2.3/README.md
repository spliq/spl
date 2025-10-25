# Experience Acquisition Pattern (L1C)

**Version**: 2.3  
**Status**: Stable  
**Category**: Cognitive Pattern  
**Layer**: L1C (Cognitive Patterns)

---

## Overview

The **Experience Acquisition Pattern** is a cognitive pattern that enables patterns to learn from interactions, observations, and outcomes. It provides frameworks for extracting knowledge from experience and adapting behavior based on what is learned.

This is **how a pattern learns and improves**, not just how it executes predefined behavior.

---

## Purpose

Experience Acquisition enables:

1. **Learning from feedback**: Improve based on outcomes
2. **Pattern recognition**: Identify regularities in experiences
3. **Behavioral adaptation**: Adjust strategies based on learning
4. **Knowledge evolution**: Continuously update understanding
5. **Transfer learning**: Apply learning across contexts

---

## Key Characteristics

### Learning vs. Execution

- **Critical Patterns (L1)**: Execute predefined logic
- **Experience Acquisition (L1C)**: Modifies future execution based on past experiences

### Types of Learning

**Supervised Learning**: Learn from labeled examples
```yaml
experience_data:
  input: "patient symptoms"
  action: "diagnosis"
  correct_label: "confirmed_disease"
  feedback: "match or mismatch"
```

**Reinforcement Learning**: Learn from rewards/penalties
```yaml
experience_data:
  state: "current situation"
  action: "chosen action"
  reward: 0.8  # Positive outcome
  next_state: "resulting situation"
```

**Unsupervised Learning**: Learn patterns without labels
```yaml
experience_data:
  observations: ["event1", "event2", "event3"]
  discovered_pattern: "events cluster into 3 groups"
```

**Transfer Learning**: Apply learning across domains
```yaml
source_domain: "image recognition"
target_domain: "medical imaging"
transferred_knowledge: "edge detection, feature extraction"
```

---

## Core Concepts

### Experience Triplet

The fundamental unit of learning:
```yaml
experience:
  context: "What was the situation?"
  action: "What did I do?"
  outcome: "What happened as a result?"
```

### Learning Cycle

```
Experience → Extract Patterns → Update Knowledge → Adapt Behavior → New Experience
     ↑                                                                      ↓
     └───────────────────── Continuous Loop ─────────────────────────────┘
```

### Confidence and Evidence

```yaml
learned_pattern:
  pattern: "when temperature > 38°C, likely infection"
  confidence: 0.87  # Based on evidence
  evidence_count: 156  # Number of supporting experiences
  counter_evidence: 12  # Contradictory cases
```

---

## Usage Examples

### Example 1: Robot Learning Optimal Grasping

```yaml
# Initial experience: Failed grasp
experience_1:
  context:
    object: "cylinder"
    diameter: "5cm"
    material: "metal"
  action:
    grasp_force: 10  # Newtons
    approach_angle: 90  # degrees
  outcome: "dropped"  # Failure
  feedback: -1.0  # Negative reward

# Learning process extracts pattern
learned_pattern:
  pattern: "metal cylinders need higher force"
  confidence: 0.6  # Low confidence, only one example
  
# Next experience: Adjusted approach
experience_2:
  context:
    object: "cylinder"
    diameter: "5cm"
    material: "metal"
  action:
    grasp_force: 15  # Increased based on learning
    approach_angle: 90
  outcome: "secured"  # Success
  feedback: 1.0  # Positive reward

# Updated learning
learned_pattern:
  pattern: "metal cylinders need 15N+ force"
  confidence: 0.75  # Higher confidence with success
  evidence_count: 2

# After 50 experiences
learned_knowledge:
  patterns:
    - pattern: "metal objects: force = 0.3 * weight"
      confidence: 0.92
      evidence_count: 50
      generalization: "applies to various shapes"
```

### Example 2: Customer Service Agent Learning Responses

```yaml
# Experience stream from customer interactions
experiences:
  - context:
      question_type: "refund_request"
      customer_sentiment: "angry"
    action:
      response: "policy_explanation"
    outcome:
      customer_satisfaction: 2/10
    feedback: "escalated to supervisor"
  
  - context:
      question_type: "refund_request"
      customer_sentiment: "angry"
    action:
      response: "empathy_first_then_policy"
    outcome:
      customer_satisfaction: 7/10
    feedback: "issue resolved"

# Learned behavior
learned_knowledge:
  patterns:
    - context: "angry customer + refund"
      effective_strategy: "empathy_first"
      ineffective_strategy: "policy_first"
      confidence: 0.88
      evidence: 23

behavior_update:
  strategy_adjustments:
    - old: "always start with policy"
      new: "empathy first when sentiment negative"
  
learning_metrics:
  satisfaction_improvement: 0.35  # 35% increase
  escalation_reduction: 0.42  # 42% fewer escalations
```

---

## Integration with Other Patterns

### With Knowledge Representation (L1C)

```yaml
# Experience updates knowledge structure
experience_acquisition:
  learns: "new medical symptoms"
  updates: "knowledge_representation"
  
knowledge_representation:
  before:
    disease_X:
      symptoms: ["fever", "cough"]
  
  after_learning:
    disease_X:
      symptoms: ["fever", "cough", "fatigue"]  # New symptom learned
      confidence: 0.91
```

### With Expectation (L1C)

```yaml
# Learning improves prediction accuracy
experience_acquisition:
  observes: "actual outcomes"
  compares: "expected outcomes (from Expectation)"
  updates: "prediction models"

expectation:
  before_learning:
    prediction_accuracy: 0.65
  
  after_learning:
    prediction_accuracy: 0.82  # Improved through experience
```

### With Critical Patterns (L1)

**With Validator**:
```yaml
# Validate learned knowledge before applying
validator:
  validates: "learned_patterns"
  checks:
    - "Sufficient evidence (n > 30)"
    - "Confidence > threshold"
    - "No contradiction with validated knowledge"
```

**With Uncertainty Handler**:
```yaml
# Manage uncertainty in learned knowledge
uncertainty_handler:
  tracks: "confidence intervals on learned patterns"
  updates: "as more evidence accumulates"
```

---

## Learning Strategies

### Incremental Learning

Add new knowledge without forgetting old:
```yaml
strategy: "incremental"
approach:
  - "Start with existing knowledge"
  - "Add new experiences gradually"
  - "Preserve previous learning"
  - "Avoid catastrophic forgetting"
```

### Active Learning

Seek informative experiences:
```yaml
strategy: "active"
approach:
  - "Identify knowledge gaps"
  - "Seek experiences that fill gaps"
  - "Prioritize uncertain areas"
  - "Maximize information gain"
```

### Meta-Learning

Learn how to learn:
```yaml
strategy: "meta-learning"
approach:
  - "Learn which learning strategies work best"
  - "Adapt learning rate based on domain"
  - "Transfer learning strategies across tasks"
```

---

## Safety and Human Oversight

### Safety-Critical Learning

When learning affects safety:
```yaml
safety_requirements:
  - "Human validates learned knowledge before deployment"
  - "Simulation testing before real-world application"
  - "Gradual rollout with monitoring"
  - "Ability to rollback to previous knowledge"
```

### Bias Detection

Prevent learning harmful biases:
```yaml
bias_detection:
  monitors:
    - "Fairness metrics across demographics"
    - "Representativeness of training experiences"
    - "Disparate impact analysis"
  
  mitigation:
    - "Balanced experience sampling"
    - "Debiasing techniques"
    - "Human review of learned patterns"
```

### Unlearning

Remove incorrect knowledge:
```yaml
unlearning:
  triggers:
    - "Learned pattern found to be incorrect"
    - "Compliance requirement (e.g., right to be forgotten)"
  
  process:
    - "Identify affected knowledge"
    - "Remove or update incorrect patterns"
    - "Revalidate dependent knowledge"
```

---

## Common Pitfalls

1. **Overfitting**: Learning too specifically to training experiences
   - **Solution**: Validate generalization, use regularization

2. **Catastrophic forgetting**: New learning erases old knowledge
   - **Solution**: Incremental learning, experience replay

3. **Bias amplification**: Learning and reinforcing biases
   - **Solution**: Bias detection, balanced experiences

4. **Ignoring negative examples**: Only learning from successes
   - **Solution**: Learn from failures, negative feedback

5. **No confidence tracking**: Treating all learned knowledge equally
   - **Solution**: Track evidence count and confidence scores

---

## Relationship to AGI

Experience Acquisition is essential for AGI:

1. **Continuous improvement**: AGI must learn from all interactions
2. **Adaptation**: AGI must adapt to changing environments
3. **Transfer learning**: AGI must apply knowledge across domains
4. **Open-ended learning**: AGI must acquire new knowledge indefinitely

Without Experience Acquisition, AGI cannot evolve beyond its initial programming.

---

## Performance Metrics

```yaml
learning_metrics:
  # Knowledge growth
  knowledge_growth_rate: 0.15  # 15% increase per 1000 experiences
  pattern_discovery_rate: 5.2  # New patterns per 100 experiences
  
  # Quality
  prediction_accuracy: 0.87  # Before: 0.65
  generalization_score: 0.79  # Performance on novel scenarios
  
  # Efficiency
  experiences_to_competence: 500  # Experiences needed for 80% accuracy
  learning_rate: 0.02  # How quickly learning occurs
```

---

## Further Reading

- `cognitive-pattern/knowledge-representation:v2.3` - Structuring learned knowledge
- `cognitive-pattern/expectation:v2.3` - Using learning to predict
- `critical-pattern/uncertainty-handler:v2.3` - Managing learning uncertainty
- Machine learning theory and algorithms
- Continual learning and lifelong learning research

---

**Status**: Production ready  
**Maintained by**: SPL Cognitive Patterns Working Group  
**Last Updated**: October 2025
