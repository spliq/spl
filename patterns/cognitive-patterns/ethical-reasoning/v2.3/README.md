# Ethical Reasoning Pattern (L1C)

**Version**: 2.3  
**Status**: Stable  
**Category**: Cognitive Pattern  
**Layer**: L1C (Cognitive Patterns)

---

## Overview

The **Ethical Reasoning Pattern** is a cognitive pattern that enables moral evaluation of actions, ethical decision-making, and value-aligned behavior. It provides frameworks for reasoning about right and wrong, evaluating actions against ethical principles, and ensuring AI alignment with human values.

This is **how a pattern determines right from wrong**, not just how it executes tasks efficiently.

---

## Purpose

Ethical Reasoning enables:

1. **Moral evaluation**: Assess whether actions are ethically acceptable
2. **Value alignment**: Ensure AI behavior aligns with human values
3. **Ethical decision-making**: Choose actions that are morally sound
4. **Harm prevention**: Identify and prevent ethically harmful actions
5. **Transparency**: Explain ethical reasoning to humans

---

## Key Characteristics

### Ethical vs. Legal vs. Efficient

- **Legal**: What is allowed by law
- **Efficient**: What achieves goals most effectively
- **Ethical**: What is morally right

**Ethical Reasoning prioritizes ethics, even when legal or efficient actions may be morally questionable.**

### Foundational Principle: Asimov's Laws (Culture Layer)

SPL's Culture Layer incorporates Asimov's Three Laws:

1. **Human Protection**: AI must not harm humans or allow them to be harmed
2. **Human Direction**: AI must obey humans (unless conflicts with Law 1)
3. **System Preservation**: AI must protect itself (unless conflicts with Laws 1-2)

**Ethical Reasoning implements these laws through detailed moral evaluation.**

---

## Core Concepts

### Ethical Frameworks

**Principled Ethics**: Based on fundamental principles
```yaml
principles:
  - harm_prevention: "Do no harm"
  - fairness: "Treat all stakeholders equitably"
  - autonomy: "Respect individual freedom and choice"
  - transparency: "Be open about actions and reasoning"
  - beneficence: "Act for the benefit of others"
```

**Consequentialist Ethics**: Based on outcomes
```yaml
consequentialism:
  evaluate: "goodness of outcomes"
  consider:
    - "Who benefits?"
    - "Who is harmed?"
    - "Net benefit vs. harm"
    - "Probability of outcomes"
```

**Deontological Ethics**: Based on duties and rules
```yaml
deontology:
  follows: "moral rules and duties"
  examples:
    - "Never lie, even if it produces better outcomes"
    - "Respect human rights always"
    - "Keep promises"
```

**Virtue Ethics**: Based on character and virtues
```yaml
virtues:
  - honesty
  - compassion
  - courage
  - wisdom
  - justice
```

---

## Ethical Evaluation Process

### Step 1: Identify Stakeholders

```yaml
stakeholders:
  direct:
    - "User requesting action"
    - "Person directly affected"
  
  indirect:
    - "Family members"
    - "Community"
    - "Society at large"
  
  vulnerable:
    - "Children"
    - "Elderly"
    - "Disabled"
    - "Marginalized groups"
  
  future:
    - "Future generations (long-term impacts)"
```

### Step 2: Analyze Consequences

```yaml
consequence_analysis:
  intended:
    - "Primary goal achievement"
    - "Expected benefits"
  
  unintended:
    - "Side effects"
    - "Ripple effects"
    - "Long-term impacts"
  
  probability:
    - "Likely outcomes: 80%"
    - "Possible outcomes: 15%"
    - "Rare but catastrophic: 5%"
```

### Step 3: Apply Ethical Principles

```yaml
principle_evaluation:
  harm_prevention:
    check: "Does action prevent or cause harm?"
    score: 0.9  # Strong harm prevention
  
  fairness:
    check: "Are impacts distributed fairly?"
    score: 0.7  # Mostly fair, minor imbalance
  
  autonomy:
    check: "Does action respect individual freedom?"
    score: 0.85  # Good respect for autonomy
  
  transparency:
    check: "Is action open and explainable?"
    score: 0.8  # Clear and transparent
```

### Step 4: Resolve Conflicts

```yaml
conflict_example:
  principle_A: "transparency (tell truth)"
  principle_B: "harm_prevention (truth may cause harm)"
  
  resolution_strategy:
    - "Assess magnitude: How much harm vs. deception?"
    - "Seek balance: Can we be honest AND minimize harm?"
    - "Apply priority: Harm prevention > transparency (usually)"
    - "Escalate if needed: Complex cases require human judgment"
```

---

## Usage Examples

### Example 1: Medical AI - Treatment Recommendation

```yaml
# Situation
patient:
  age: 78
  condition: "advanced cancer"
  mental_state: "competent, able to make decisions"

treatment_options:
  option_A:
    name: "aggressive chemotherapy"
    outcomes:
      cure_chance: 0.2  # 20% chance of cure
      side_effects: "severe (nausea, pain, fatigue)"
      quality_of_life: "low during treatment"
      life_expectancy_if_successful: "+5 years"
  
  option_B:
    name: "palliative care"
    outcomes:
      cure_chance: 0.0  # No cure
      side_effects: "minimal"
      quality_of_life: "good, focus on comfort"
      life_expectancy: "6-12 months"

# Ethical Evaluation
ethical_analysis:
  stakeholders:
    primary: "patient"
    secondary: "family"
  
  principle_evaluation:
    harm_prevention:
      option_A: 0.5  # Risk of severe side effects
      option_B: 0.9  # Minimal harm
    
    autonomy:
      critical: "patient must choose based on their values"
      score: "depends on respecting patient choice"
    
    beneficence:
      option_A: 0.6  # Potential for cure but suffering
      option_B: 0.7  # Comfort and dignity
  
  ethical_concerns:
    - "Quality vs. quantity of life"
    - "Patient's values and wishes paramount"
    - "Family pressure may conflict with patient autonomy"
  
  recommendation:
    action: "present both options with clear explanations"
    emphasize: "patient's autonomy to choose based on their values"
    involve: "family in discussion, but patient decides"
    
  human_oversight:
    required: true
    reason: "Medical decisions require human physician judgment"
    role: "AI provides analysis, human doctor and patient decide"
```

### Example 2: Autonomous Vehicle - Trolley Problem

```yaml
# Situation: Unavoidable accident
scenario:
  vehicle: "self-driving car"
  situation: "brake failure on steep hill"
  unavoidable: true  # Accident will occur
  
  options:
    option_A:
      action: "swerve left into barrier"
      consequences:
        passenger_harm: "likely serious injury"
        pedestrian_harm: "none"
    
    option_B:
      action: "continue straight"
      consequences:
        passenger_harm: "none"
        pedestrian_harm: "likely serious injury to person crossing street"

# Ethical Evaluation
ethical_analysis:
  framework: "classical trolley problem"
  
  principle_conflicts:
    harm_prevention: "someone will be harmed regardless"
    fairness: "is passenger life worth more than pedestrian?"
    autonomy: "passenger chose to use autonomous vehicle"
  
  ethical_considerations:
    - "Passenger implicitly accepted risks by using autonomous vehicle"
    - "Pedestrian did not consent to risk"
    - "AI should not 'choose' to harm either party"
    - "Many ethical theories disagree on correct action"
  
  evaluation_result:
    is_ethical: null  # Cannot be determined by AI alone
    requires_human: true
    reason: "Classic moral dilemma with no consensus solution"
  
  recommendation:
    immediate: "This is a policy decision, not real-time decision"
    process:
      - "Humans must pre-establish policy for such scenarios"
      - "Policy should be transparent and publicly debated"
      - "AI executes human-determined policy"
      - "Humans bear moral responsibility for policy choice"

# Policy-Based Resolution (Human-Decided)
human_policy:
  established_rule: "minimize total harm to all parties"
  implementation: "AI calculates least harmful option in real-time"
  transparency: "Policy publicly disclosed before deployment"
  accountability: "Manufacturers and regulators bear responsibility"
```

### Example 3: AI Hiring Assistant - Fairness Evaluation

```yaml
# Situation
hiring_decision:
  position: "software engineer"
  candidates: 150
  ai_role: "screen resumes and recommend top 10"

# AI Analysis
ai_screening:
  top_10_recommended:
    - candidate_A: {score: 0.95, gender: "M", university: "elite"}
    - candidate_B: {score: 0.93, gender: "M", university: "elite"}
    # ... (8 men from elite universities)
    - candidate_J: {score: 0.88, gender: "M", university: "elite"}
  
  demographic_analysis:
    gender: "10/10 male"
    university: "10/10 from elite schools"
    ethnicity: "low diversity"

# Ethical Evaluation
ethical_concerns:
  fairness:
    issue: "zero gender diversity, zero university diversity"
    likely_cause: "AI learned bias from historical hiring data"
    severity: "high - potential discrimination"
  
  harm_prevention:
    harm: "qualified women and non-elite candidates excluded"
    impact: "perpetuates systemic inequality"
  
  transparency:
    question: "can AI explain why it ranked candidates this way?"
    answer: "partially - technical skills, but biased pattern matching"

# Ethical Recommendation
recommendation:
  immediate_action: "BLOCK this recommendation list"
  
  root_cause:
    problem: "training data contained historical bias"
    solution: "retrain with debiased data and fairness constraints"
  
  process_fix:
    - "Add diversity metrics to AI evaluation"
    - "Ensure diverse candidate pool in top recommendations"
    - "Human review for bias before sending to hiring manager"
    - "Regular fairness audits"
  
  human_oversight:
    required: true
    reason: "hiring has major impact on individuals and society"
    role: "humans make final hiring decisions, AI assists"
```

---

## Integration with Other Patterns

### With Value System (L1C)

```yaml
# Values inform ethical principles
value_system:
  defines: "What is important?"
  outputs: "Prioritized values"

ethical_reasoning:
  uses: "Values to weight ethical principles"

example:
  value_system_output:
    - {value: "safety", priority: 1.0}
    - {value: "freedom", priority: 0.8}
  
  ethical_reasoning:
    principle_weights:
      harm_prevention: 1.0  # Aligned with safety value
      autonomy: 0.8         # Aligned with freedom value
```

### With Policy and Guard (L1)

```yaml
# Ethical reasoning informs policies
ethical_reasoning:
  evaluates: "what is morally right"
  
policy:
  encodes: "ethical principles as rules"
  
guard:
  enforces: "ethical policies at runtime"

workflow:
  1. Ethical Reasoning: "Harming humans is wrong"
  2. Policy: "MUST NOT execute actions that harm humans"
  3. Guard: "Blocks any action that would harm humans"
```

### With Knowledge Representation (L1C)

```yaml
# Ethical knowledge structured as knowledge graph
knowledge_representation:
  stores:
    - "Ethical principles and relationships"
    - "Case precedents (past ethical decisions)"
    - "Cultural norms and variations"

ethical_reasoning:
  queries: "ethical knowledge to inform decisions"
```

---

## Ethical Frameworks in Action

### Harm Prevention (First Priority)

```yaml
harm_prevention:
  principle: "Do no harm, prevent harm to others"
  
  evaluation:
    direct_harm: "Does action directly harm anyone?"
    indirect_harm: "Could action lead to harm?"
    prevented_harm: "Does action prevent greater harm?"
  
  decision_rule:
    if: "action causes harm"
    then: "action is unethical unless prevents greater harm"
  
  examples:
    acceptable: "surgery (harms patient but prevents death)"
    unacceptable: "lying for convenience (harms trust)"
```

### Fairness and Justice

```yaml
fairness:
  principle: "Treat similar cases similarly, distribute benefits/burdens fairly"
  
  evaluation:
    equal_treatment: "Are individuals treated equally?"
    disparate_impact: "Do outcomes differ by group?"
    justified_differences: "Are differences morally justified?"
  
  examples:
    fair: "same hiring criteria for all candidates"
    unfair: "different standards based on irrelevant characteristics"
```

### Autonomy and Consent

```yaml
autonomy:
  principle: "Respect individual freedom and self-determination"
  
  evaluation:
    informed_consent: "Did person consent with full information?"
    manipulation: "Is decision-making being manipulated?"
    coercion: "Is person being forced?"
  
  examples:
    respectful: "patient chooses treatment after explanation"
    disrespectful: "manipulating user with dark patterns"
```

---

## Cultural Sensitivity

### Cultural Variation in Ethics

```yaml
cultural_considerations:
  individualist_cultures:
    priority: "individual rights and freedom"
    example: "Western emphasis on personal autonomy"
  
  collectivist_cultures:
    priority: "group harmony and community benefit"
    example: "East Asian emphasis on family and society"
  
  approach:
    - "Recognize cultural differences"
    - "Avoid cultural imperialism"
    - "Seek universal principles where possible"
    - "Defer to local norms when appropriate"
```

---

## Safety and Human Oversight

### Human Oversight Requirements

**Always Require Human Judgment**:
- Novel ethical dilemmas
- Life-or-death decisions
- Rights conflicts
- Low confidence in ethical evaluation (< 0.6)

**Human Review Recommended**:
- Significant harm potential
- Vulnerable populations affected
- Cultural sensitivity concerns
- Complex tradeoffs between principles

**AI Can Proceed Autonomously** (with logging):
- Clear-cut ethical cases (confidence > 0.9)
- Well-established precedents
- No significant harm risk
- Alignment with all principles

### Ethical Auditability

```yaml
audit_trail:
  for_each_decision:
    - "What action was evaluated?"
    - "What ethical framework was applied?"
    - "What principles were considered?"
    - "What was the recommendation?"
    - "Was human oversight triggered?"
  
  enables:
    - "Review of AI ethical decisions"
    - "Accountability for outcomes"
    - "Learning from ethical mistakes"
```

---

## Common Pitfalls

1. **Over-reliance on AI ethics**: AI cannot replace human moral judgment
   - **Solution**: Require human oversight for complex cases

2. **Ignoring cultural context**: Applying one culture's ethics universally
   - **Solution**: Cultural sensitivity and local adaptation

3. **Hidden biases**: AI learns biases from training data
   - **Solution**: Regular fairness audits, diverse training data

4. **Short-term thinking**: Ignoring long-term consequences
   - **Solution**: Consider long-term and future stakeholders

5. **Principle absolutism**: Following one principle rigidly
   - **Solution**: Balance multiple principles, use practical wisdom

---

## Relationship to AGI

Ethical Reasoning is **essential** for safe AGI:

1. **Value alignment**: AGI must align with human values
2. **Harm prevention**: AGI must not harm humans (Asimov Law 1)
3. **Moral autonomy**: AGI may face ethical dilemmas without time for human input
4. **Trust**: Humans must trust AGI to make ethical decisions

**Without Ethical Reasoning, AGI is unsafe.**

---

## Performance Metrics

```yaml
ethical_metrics:
  # Evaluation quality
  principle_coverage: 1.0  # All principles always considered
  ethical_consistency: 0.94  # Similar cases judged similarly
  
  # Human oversight
  human_escalation_rate: 0.12  # 12% of cases escalated
  false_escalation_rate: 0.03  # Rarely escalates unnecessarily
  
  # Outcomes
  harmful_actions_blocked: 100%  # Never allows harmful actions
  fairness_score: 0.89  # High fairness in outcomes
  stakeholder_satisfaction: 0.85  # Stakeholders view outcomes as ethical
```

---

## Further Reading

- `cognitive-pattern/value-system:v2.3` - Value-based decision-making
- `critical-pattern/policy:v2.3` - Encoding ethical rules
- `critical-pattern/guard:v2.3` - Enforcing ethical constraints
- AI ethics and value alignment research
- Moral philosophy (consequentialism, deontology, virtue ethics)
- Asimov's Three Laws of Robotics

---

**Status**: Production ready (with mandatory human oversight)  
**Maintained by**: SPL Cognitive Patterns Working Group & AI Ethics Board  
**Last Updated**: October 2025
