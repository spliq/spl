# Motivation Pattern (L1C)

**Version**: 2.3  
**Status**: Stable  
**Category**: Cognitive Pattern  
**Layer**: L1C (Cognitive Patterns)

---

## Overview

The **Motivation Pattern** is a cognitive pattern that enables goal-directed behavior, action selection, and persistence in pursuit of objectives. It provides frameworks for prioritizing actions based on internal drive states, goal importance, and expected outcomes.

This is **what drives a pattern to act**, not just how it executes when commanded.

---

## Purpose

Motivation enables:

1. **Goal-directed behavior**: Act toward achieving objectives
2. **Action prioritization**: Choose what to do next among many options
3. **Persistence**: Continue despite obstacles or setbacks
4. **Goal adaptation**: Adjust goals based on progress and context
5. **Intrinsic vs. extrinsic motivation**: Balance internal satisfaction and external rewards

---

## Key Characteristics

### Motivation vs. Execution

- **Critical Patterns (L1)**: Execute specific tasks when invoked
- **Motivation (L1C)**: Decide which tasks to pursue and when

### Types of Motivation

**Intrinsic**: Internal satisfaction from the action itself
```yaml
intrinsic_motivation:
  goal: "learn new skills"
  drive: "curiosity, mastery, growth"
  reward: "feeling of accomplishment"
```

**Extrinsic**: External rewards or consequences
```yaml
extrinsic_motivation:
  goal: "complete task"
  drive: "obtain reward, avoid penalty"
  reward: "payment, recognition, avoiding punishment"
```

**Social**: Motivation from social context
```yaml
social_motivation:
  goal: "contribute to team"
  drive: "collaboration, belonging, approval"
  reward: "positive feedback, team success"
```

---

## Core Concepts

### Goal Structure

```yaml
goal:
  id: "G1"
  description: "Complete project X"
  priority: 0.9  # Importance (0.0-1.0)
  progress: 0.6  # Completion (0.0-1.0)
  deadline: "2025-11-01"
  status: "active"  # active, completed, abandoned
```

### Utility Calculation

How valuable is pursuing a goal right now?

```yaml
utility_formula: |
  utility = (intrinsic_value + extrinsic_value) × urgency × feasibility - cost
  
  where:
    intrinsic_value = satisfaction from goal itself
    extrinsic_value = external rewards
    urgency = deadline_proximity × priority
    feasibility = likelihood_of_success
    cost = resources_required + opportunity_cost
```

### Persistence and Drive

```yaml
persistence:
  definition: "willingness to continue despite obstacles"
  factors:
    - goal_importance: "higher priority → higher persistence"
    - progress: "more progress → higher persistence"
    - obstacles: "repeated failures → lower persistence"
  
  recovery:
    - "Success increases persistence"
    - "Rest periods restore persistence"
    - "Subgoal completion boosts persistence"
```

---

## Usage Examples

### Example 1: Personal Assistant Task Prioritization

```yaml
# Current state
current_state:
  time: "10:00 AM"
  environment: "office"
  goals:
    - id: "report"
      description: "Finish quarterly report"
      priority: 0.9
      deadline: "12:00 PM"  # 2 hours away
      progress: 0.7
    
    - id: "meeting"
      description: "Schedule team meeting"
      priority: 0.6
      deadline: "5:00 PM"  # 7 hours away
      progress: 0.0
    
    - id: "emails"
      description: "Respond to emails"
      priority: 0.5
      deadline: "end of day"
      progress: 0.3

  possible_actions:
    - "work_on_report"
    - "schedule_meeting"
    - "respond_to_emails"
    - "take_break"

# Motivation analysis
motivation_analysis:
  report:
    intrinsic_value: 0.7  # Important work
    extrinsic_value: 0.9  # Boss expects it
    urgency: 0.95  # Very soon deadline, high priority
    feasibility: 0.85  # Almost done, likely to finish
    utility: 0.89
  
  meeting:
    intrinsic_value: 0.4
    extrinsic_value: 0.5
    urgency: 0.4  # Can wait
    feasibility: 0.9  # Easy task
    utility: 0.52
  
  emails:
    intrinsic_value: 0.3
    extrinsic_value: 0.4
    urgency: 0.3
    feasibility: 0.8
    utility: 0.38

# Selected action
selected_action:
  action: "work_on_report"
  rationale: "Highest utility (0.89): near deadline, high priority, good progress"
  expected_result: "Complete report by deadline"

# After report is completed
goal_updates:
  - goal_id: "report"
    status: "completed"
    persistence_boost: +0.2  # Success increases drive
  
  - goal_id: "meeting"
    priority: 0.7  # Now becomes more urgent
```

### Example 2: Autonomous Robot Exploration vs. Task Completion

```yaml
# Robot in warehouse
current_state:
  location: "warehouse sector B"
  battery: 70%
  goals:
    - id: "deliver_package"
      description: "Deliver package to dock 5"
      priority: 0.8
      progress: 0.5  # Halfway there
    
    - id: "map_warehouse"
      description: "Complete warehouse map"
      priority: 0.5
      progress: 0.6
      intrinsic: true  # Curiosity-driven

  possible_actions:
    - "continue_to_dock_5"  # Exploitation: complete known task
    - "explore_sector_C"    # Exploration: learn new area
    - "return_to_charger"   # Maintenance

# Motivation analysis
motivation_state:
  drive_levels:
    task_completion: 0.8  # High drive to complete delivery
    exploration: 0.6      # Moderate curiosity
    self_preservation: 0.3  # Battery okay for now
  
  action_selection:
    continue_delivery:
      utility: 0.85  # High extrinsic value, clear goal
    
    explore:
      utility: 0.55  # Lower utility, but intrinsic value
    
    charge:
      utility: 0.25  # Not urgent yet

selected_action: "continue_to_dock_5"
rationale: "Task completion has higher utility, battery sufficient"

# After delivery completed
updated_state:
  goals:
    - id: "deliver_package"
      status: "completed"  # Done!
  
  drive_levels:
    task_completion: 0.0  # No immediate tasks
    exploration: 0.8      # Now dominant drive!

next_selected_action: "explore_sector_C"
rationale: "With no pressing tasks, intrinsic exploration motivation dominates"
```

---

## Integration with Other Patterns

### With Value System (L1C)

```yaml
# Values inform goal priorities
value_system:
  defines: "What matters most"
  outputs: "Prioritized values"

motivation:
  uses: "Value rankings to set goal priorities"
  
example:
  value_system_output:
    - {value: "safety", priority: 1.0}
    - {value: "efficiency", priority: 0.7}
  
  motivation_result:
    - {goal: "ensure_safety", priority: 1.0}  # Aligned with top value
    - {goal: "optimize_route", priority: 0.7}  # Aligned with efficiency
```

### With Expectation (L1C)

```yaml
# Expectations inform feasibility
expectation:
  predicts: "Likely outcomes of actions"

motivation:
  uses: "Predictions to calculate feasibility and expected utility"

example:
  expectation_output:
    action: "work_on_report"
    predicted_progress: 0.3  # Expect to complete 30% more
    confidence: 0.85
  
  motivation_calculation:
    feasibility: 0.85  # Based on expectation confidence
    expected_utility: high  # Good progress expected
```

### With Planner (L1)

```yaml
# Motivation selects goals; Planner figures out how
motivation:
  selects: "Goal to pursue"
  
planner:
  creates: "Step-by-step plan to achieve goal"

workflow:
  1. Motivation: "I want to achieve goal G1"
  2. Planner: "Here's how: step1 → step2 → step3"
  3. Motivation: "Execute plan, maintain persistence"
```

---

## Motivation Dynamics

### Goal Conflicts

When multiple goals compete:
```yaml
conflict_scenario:
  goal_A: "Complete urgent task (deadline: 1 hour)"
  goal_B: "Help teammate (high social value)"
  
conflict_resolution:
  strategy: "utility_comparison"
  if: "utility(A) > utility(B)"
  then: "pursue A"
  else_if: "utility(B) > utility(A)"
  then: "pursue B"
  else:  # Tie
  then: "request human decision"
```

### Persistence Recovery

Maintaining motivation over time:
```yaml
persistence_management:
  initial_persistence: 0.8
  
  after_setback:
    persistence: 0.5  # Dropped due to obstacle
  
  recovery_strategies:
    - "Break goal into smaller subgoals"
    - "Celebrate partial progress"
    - "Take rest period"
    - "Seek support or resources"
  
  after_subgoal_success:
    persistence: 0.7  # Recovered through success
```

### Motivation Decay and Refresh

Goals lose urgency over time if not pursued:
```yaml
motivation_over_time:
  day_1:
    goal: "Clean garage"
    urgency: 0.6
  
  day_7:  # If not pursued
    urgency: 0.4  # Decayed
  
  refresh_triggers:
    - "Deadline approaches"
    - "External reminder"
    - "Related goal completed"
  
  day_8_with_reminder:
    urgency: 0.7  # Refreshed
```

---

## Safety and Human Oversight

### Goal Validation

Ensure goals are safe and aligned:
```yaml
goal_validation:
  checks:
    - "Does goal violate safety constraints?"
    - "Is goal aligned with human values?"
    - "Could goal lead to harmful actions?"
  
  if_unsafe:
    action: "Block goal, alert human"
```

### Burnout Prevention

Monitor for unsustainable motivation:
```yaml
burnout_detection:
  monitors:
    - "Persistence consistently low (< 0.3)"
    - "No progress despite high effort"
    - "No rest periods in extended time"
  
  intervention:
    - "Force rest period"
    - "Suggest goal adjustment"
    - "Alert human operator"
```

### Human Override

Humans can always redirect motivation:
```yaml
human_override:
  user_command: "Stop current goal, prioritize X"
  
  system_response:
    - "Pause current goal pursuit"
    - "Set X to highest priority"
    - "Explain change to user"
    - "Resume when X completed or user directs"
```

---

## Common Pitfalls

1. **Single-goal fixation**: Neglecting other important goals
   - **Solution**: Multi-goal utility calculation, balance priorities

2. **Goal proliferation**: Too many active goals
   - **Solution**: Goal pruning, focus on top priorities

3. **Extrinsic over-optimization**: Ignoring intrinsic value
   - **Solution**: Balance intrinsic and extrinsic factors

4. **No goal adaptation**: Pursuing obsolete goals
   - **Solution**: Regular goal review and update

5. **Zero persistence**: Giving up too easily
   - **Solution**: Persistence thresholds, recovery mechanisms

---

## Relationship to AGI

Motivation is fundamental to AGI:

1. **Autonomous goal pursuit**: AGI must pursue goals without constant human direction
2. **Long-term planning**: AGI must maintain motivation across extended timescales
3. **Goal discovery**: AGI may need to generate new goals (with human oversight)
4. **Value alignment**: AGI's motivation must align with human values

Without Motivation, AGI is a passive tool requiring constant instruction, not an autonomous agent.

---

## Performance Metrics

```yaml
motivation_metrics:
  # Goal achievement
  goal_completion_rate: 0.87  # 87% of goals completed
  average_time_to_completion: "2.3 days"
  
  # Action quality
  action_alignment_with_goals: 0.92  # 92% of actions advance goals
  utility_prediction_accuracy: 0.81  # How well utility matches outcomes
  
  # Sustainability
  average_persistence: 0.74
  burnout_incidents: 0  # None detected
  
  # Efficiency
  goal_switch_overhead: 0.05  # 5% time lost in switching
  action_selection_time: "45ms"  # Fast decision-making
```

---

## Further Reading

- `cognitive-pattern/value-system:v2.3` - What to value in goals
- `cognitive-pattern/expectation:v2.3` - Predicting goal outcomes
- `critical-pattern/planner:v2.3` - How to achieve goals
- Goal-setting theory and achievement motivation
- Self-determination theory (intrinsic/extrinsic motivation)

---

**Status**: Production ready  
**Maintained by**: SPL Cognitive Patterns Working Group  
**Last Updated**: October 2025
