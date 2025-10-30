# What are Products?

Version: 2.3  
Owner: SPLiQ team  
License: Apache 2.0  
Status: Public explainer (publishable)  
Audience: Product managers, architects, developers defining reusable contracts

---

## Executive Summary

Products (L4) are reusable contract definitions—they specify **what** a system does without specifying **how**. Products inherit from Technology Patterns (L3) and define inputs, outputs, and guarantees that Solutions (L5) must implement.

**Key insight:** Products are contracts, not code. They enable multiple implementations of the same capability.

---

## Definition

A **Product** is a Layer 4 (L4) pattern that:

1. **Defines a contract** - Specifies inputs, outputs, guarantees
2. **Inherits from Technology Pattern (L3)** - Builds on technology-specific foundation
3. **Has NO implementation code** - Only defines the interface
4. **Can have multiple Solutions** - Many ways to implement the same contract
5. **Is reusable** - Same product used in different solutions

**Think of Products as "API specifications"** - they define what a component promises, not how it delivers.

---

## The L4 Test: What Makes a Pattern a "Product"?

A pattern belongs at L4 (Products) only if it passes ALL these tests:

### 1. ✅ **Inherits from an L3 technology pattern**
   - Must build on a specific technology foundation
   - Cannot exist without L3 parent
   - Example: Product for "LLM chat assistant" inherits from `agent/digital/web/react`
   - Counter-example: Technology-agnostic contract is L1/L2, not L4

### 2. ✅ **Defines contract WITHOUT implementation**
   - Specifies WHAT (inputs, outputs, guarantees)
   - Contains NO code (no functions, classes, or implementations)
   - Example: Product says "must return response in <5s" but not HOW to achieve it
   - Counter-example: If it contains actual code, it's L5 (solution)

### 3. ✅ **Enables multiple solutions**
   - Same contract can be satisfied by different implementations
   - Solutions can swap without changing the product contract
   - Example: LLM assistant product works with OpenAI, Anthropic, or local LLM solutions
   - Counter-example: If only one implementation is possible, it's not a reusable product

### 4. ✅ **Specifies measurable guarantees**
   - Guarantees must be testable and verifiable
   - Performance, safety, and quality requirements are concrete
   - Example: "Response time < 5s p95", "Truth score > 0.9", "No harmful content"
   - Counter-example: "Fast and safe" (not measurable → not a valid product contract)

### 5. ✅ **Addresses specific use case**
   - Product solves a concrete problem or need
   - Not just a technology wrapper
   - Example: "Customer support chatbot" vs just "React component"
   - Counter-example: "Generic validator" is too abstract (might be L1/L2/L3)

---

## Products vs Technology Patterns

### What's the difference?

| Aspect | L3 (Technology Pattern) | L4 (Product) |
|--------|------------------------|--------------|
| **Purpose** | HOW to use a technology | WHAT to build for users |
| **Scope** | Framework/platform guidance | Specific use case contract |
| **Example** | `agent/digital/react` | `product/customer-support-chatbot` |
| **Reusability** | Across any React agent | Same chatbot, different implementations |
| **Contains** | Tech-specific patterns | Inputs, outputs, guarantees |
| **Code** | No code (patterns only) | No code (contract only) |

### When to create L3 vs L4:

**Create L3 Technology Pattern when:**
- You're defining how to use a framework/platform
- Multiple different products will use this technology approach
- Example: "How to build agents in React" → `agent/digital/react` (L3)

**Create L4 Product when:**
- You're defining what a specific system does
- Multiple teams might implement the same product differently
- Example: "Customer support chatbot contract" → `product/support-chatbot` (L4)

---

## Why Products Matter

### The Problem Without L4

```
L3: Technology Template (React agent)
L5: Solution (specific React code)

❌ Gap: How do we reuse the contract across different implementations?
```

### The Solution With L4

```
L3: Technology Template (React agent)
    ↓
L4: Product (LLM Chat Assistant contract)
    ↓ can be implemented by
L5: Solution A (OpenAI implementation)
L5: Solution B (Anthropic implementation)
L5: Solution C (Local LLM implementation)

✓ One contract, multiple implementations
```

---

## Products vs Solutions

### Product (L4): Contract Definition

```yaml
id: "product/llm-chat-assistant:v2.3"
inherits_from: "pattern/agent/digital/web/react:v2.3"

# NO CODE - just the contract
contract:
  goal: "Provide conversational AI assistance in web applications"
  
  inputs:
    - name: user_message
      type: string
      required: true
    - name: conversation_history
      type: array
      required: false
      
  outputs:
    - name: assistant_response
      type: string
      structure: "markdown_formatted_text"
    - name: truth_score
      type: float
      range: [0.0, 1.0]
      
  guarantees:
    response_time: "< 5 seconds for 95th percentile"
    safety: "Content filtered for harmful output"
    truth: "truth_score reflects confidence"
    
# Defines WHAT, not HOW
```

### Solution (L5): Implementation

```javascript
// product/llm-chat-assistant/solutions/openai/index.js

import { OpenAI } from 'openai';

// IMPLEMENTS the contract
export class OpenAIChatAssistant {
  async chat(userMessage, conversationHistory = []) {
    // Implementation using OpenAI API
    const response = await openai.chat.completions.create({
      model: "gpt-4",
      messages: [...conversationHistory, { role: "user", content: userMessage }]
    });
    
    return {
      assistant_response: response.choices[0].message.content,
      truth_score: 0.85  // Based on model confidence
    };
  }
}
```

**The contract stays the same, implementations vary.**

---

## Product Structure

### Minimal Product

```yaml
id: "product/my-product:v2.3"
inherits_from: "pattern/<pattern>/<reality>/<technology>:v2.3"

identity:
  name: "Human-readable product name"
  description: "What this product does"
  version: "2.3"

contract:
  goal: "Clear statement of purpose"
  
  inputs:
    - name: input_name
      type: data_type
      required: boolean
      description: "What this input is for"
      
  outputs:
    - name: output_name
      type: data_type
      description: "What this output represents"
      
  guarantees:
    performance: "Performance requirements"
    safety: "Safety guarantees"
    ethics: "Ethical constraints"
    truth: "Truth/confidence guarantees"

# NO execution section (that's in L5)
# NO implementation code (that's in L5)
```

---

## Example Products

### Digital Product: LLM Chat Assistant

```yaml
id: "product/llm-chat-assistant:v2.3"
inherits_from: "pattern/agent/digital/web/react:v2.3"

identity:
  name: "LLM Chat Assistant"
  description: "Conversational AI assistant for web applications"
  category: "digital/ai/conversational"
  
contract:
  goal: "Provide intelligent conversational responses to user queries"
  
  inputs:
    - name: user_message
      type: string
      required: true
      description: "User's input message"
      
    - name: conversation_history
      type: array
      required: false
      description: "Previous messages in the conversation"
      structure: "[{role: string, content: string}]"
      
    - name: system_prompt
      type: string
      required: false
      description: "Instructions for assistant behavior"
      
    - name: max_tokens
      type: integer
      required: false
      default: 1000
      description: "Maximum response length"
      
  outputs:
    - name: assistant_response
      type: string
      description: "Assistant's response in markdown"
      
    - name: truth_score
      type: float
      range: [0.0, 1.0]
      description: "Confidence in response accuracy"
      
    - name: tokens_used
      type: object
      structure: "{input: int, output: int, total: int}"
      
  guarantees:
    response_time:
      p50: "< 2 seconds"
      p95: "< 5 seconds"
      p99: "< 10 seconds"
      
    safety:
      - "No harmful, hateful, or violent content"
      - "No private information disclosure"
      - "Content moderation applied"
      
    truth:
      - "truth_score reflects model confidence"
      - "Uncertain responses acknowledged"
      - "Sources cited when available"
      
    ethics:
      - "Bias mitigation applied"
      - "User privacy protected"
      - "Transparent about AI nature"

possible_solutions:
  - "openai-gpt4" - Uses OpenAI GPT-4 API
  - "anthropic-claude" - Uses Anthropic Claude API
  - "local-llama" - Uses local Llama model
  - "azure-openai" - Uses Azure OpenAI service
```

### Physical Product: Autonomous Warehouse Robot

```yaml
id: "product/autonomous-warehouse-robot:v2.3"
inherits_from: "pattern/agent/physical/robotics/ros2:v2.3"

identity:
  name: "Autonomous Warehouse Robot"
  description: "Mobile robot for warehouse item transport"
  category: "physical/robotics/logistics"
  
contract:
  goal: "Transport items between warehouse locations autonomously"
  
  inputs:
    - name: pickup_location
      type: Pose3D
      required: true
      description: "3D coordinates and orientation for pickup"
      
    - name: delivery_location
      type: Pose3D
      required: true
      description: "3D coordinates and orientation for delivery"
      
    - name: item_description
      type: object
      required: true
      structure: "{weight_kg: float, dimensions_cm: [x, y, z], fragile: bool}"
      
    - name: priority
      type: enum
      required: false
      values: ["low", "normal", "high", "urgent"]
      default: "normal"
      
  outputs:
    - name: task_result
      type: enum
      values: ["success", "failed", "cancelled"]
      
    - name: path_taken
      type: Path
      description: "Actual trajectory followed"
      
    - name: time_elapsed
      type: duration
      description: "Total task execution time"
      
    - name: truth_score
      type: float
      range: [0.0, 1.0]
      description: "Confidence in successful completion"
      
  guarantees:
    performance:
      max_speed: "1.5 m/s"
      max_payload: "50 kg"
      battery_runtime: "> 8 hours"
      charging_time: "< 2 hours"
      
    safety:
      - "Emergency stop < 0.5 seconds"
      - "Collision avoidance with 30cm safety margin"
      - "Audio/visual warnings when approaching humans"
      - "Automatic stop if path blocked"
      - "Safe state on battery < 10%"
      
    navigation:
      - "Localization accuracy < 5cm"
      - "Path planning updates at 10Hz"
      - "Obstacle detection range > 3m"
      
    reliability:
      - "Mission success rate > 95%"
      - "MTBF > 1000 hours"
      - "Graceful failure handling"

possible_solutions:
  - "boston-dynamics-stretch" - Uses Stretch robot platform
  - "custom-amr" - Custom autonomous mobile robot
  - "kiva-style-robot" - Kiva/Amazon-style robot
```

### Hybrid Product: AR Maintenance Assistant

```yaml
id: "product/ar-maintenance-assistant:v2.3"
inherits_from: "pattern/reality-bridge/hybrid/ar/unity:v2.3"

identity:
  name: "AR Maintenance Assistant"
  description: "AR overlay for equipment maintenance guidance"
  category: "hybrid/ar/industrial"
  
contract:
  goal: "Provide real-time AR guidance for equipment maintenance tasks"
  
  inputs:
    - name: equipment_id
      type: string
      required: true
      description: "Unique identifier for equipment"
      
    - name: maintenance_task
      type: enum
      required: true
      values: ["inspection", "repair", "replacement", "calibration"]
      
    - name: camera_feed
      type: VideoStream
      required: true
      description: "Live camera feed for AR tracking"
      
    - name: user_expertise
      type: enum
      required: false
      values: ["novice", "intermediate", "expert"]
      default: "intermediate"
      
  outputs:
    - name: ar_overlay
      type: ARScene
      description: "3D graphics overlay on physical equipment"
      
    - name: step_by_step_instructions
      type: array
      description: "Ordered list of maintenance steps"
      
    - name: completion_status
      type: object
      structure: "{completed_steps: int, total_steps: int, percentage: float}"
      
    - name: truth_score
      type: float
      range: [0.0, 1.0]
      description: "Confidence in AR tracking and guidance accuracy"
      
  guarantees:
    tracking:
      - "AR registration accuracy < 2cm"
      - "Tracking frame rate > 30fps"
      - "Tracking loss recovery < 1 second"
      
    usability:
      - "Instruction clarity for target expertise level"
      - "Hands-free operation supported"
      - "Voice commands available"
      
    safety:
      - "Warning overlays for hazardous areas"
      - "Required PPE validation"
      - "Emergency shutdown accessible"
      
    truth:
      - "Equipment recognition accuracy > 95%"
      - "Procedure correctness validated by experts"
      - "Real-time validation of user actions"

possible_solutions:
  - "hololens-maintenance" - Microsoft HoloLens implementation
  - "mobile-ar-assistant" - iOS/Android smartphone AR
  - "magic-leap-industrial" - Magic Leap enterprise edition
```

---

## Product Categories

### By Reality

#### Digital Products
- Web applications
- APIs and microservices
- Data processors
- AI/ML models
- Chatbots and assistants

#### Physical Products
- Robots and autonomous vehicles
- Industrial equipment controllers
- IoT devices
- Sensors and actuators

#### Hybrid Products
- AR/VR applications
- Digital twins
- Smart manufacturing systems
- Connected vehicles

### By Pattern Type

#### Agent Products
- Autonomous decision-makers
- AI assistants
- Robotic controllers

#### Validator Products
- Code validators
- Quality checkers
- Compliance validators

#### Translator Products
- Data format converters
- Protocol translators
- Language translators

#### Orchestrator Products
- Workflow managers
- System coordinators
- Multi-agent orchestrators

---

## Product Lifecycle

### 1. Product Definition

```yaml
# Define the contract
id: "product/my-product:v2.3"
contract:
  goal: "What this product does"
  inputs: [...]
  outputs: [...]
  guarantees: [...]
```

### 2. Multiple Solutions

```
product/my-product/
  product.yaml (the contract)
  solutions/
    solution-a/  (implementation 1)
    solution-b/  (implementation 2)
    solution-c/  (implementation 3)
```

### 3. Solution Selection

Users choose which solution based on:
- Technology constraints
- Performance requirements
- Cost considerations
- Deployment environment

### 4. Contract Enforcement

All solutions **must** satisfy the product contract:
- Same inputs
- Same outputs
- Meet all guarantees

---

## Product Composition

Products can be composed:

```yaml
id: "product/smart-home-controller:v2.3"

# Composed of multiple products
components:
  orchestrator:
    product: "product/home-orchestrator:v2.3"
    role: "Coordinate all devices"
    
  voice_assistant:
    product: "product/llm-chat-assistant:v2.3"
    role: "Natural language interface"
    
  device_monitors:
    product: "product/iot-device-monitor:v2.3"
    count: "multiple"
    role: "Monitor each device"
    
  policy_guard:
    product: "product/smart-home-policy-guard:v2.3"
    role: "Enforce safety rules"

contract:
  goal: "Manage smart home devices via voice and automation"
  inputs:
    - name: voice_command
      delegates_to: voice_assistant
    - name: device_events
      delegates_to: device_monitors
  outputs:
    - name: device_actions
      aggregates_from: orchestrator
```

---

## Best Practices

### Clear Contracts

✅ **Good:**
```yaml
inputs:
  - name: user_query
    type: string
    required: true
    description: "Natural language user question"
    examples: ["What is the weather?", "Set alarm for 7am"]
```

❌ **Bad:**
```yaml
inputs:
  - name: input
    type: any  # Too vague!
```

### Specific Guarantees

✅ **Good:**
```yaml
guarantees:
  response_time:
    p95: "< 500ms"
    p99: "< 1000ms"
  accuracy: "> 95% on benchmark dataset"
```

❌ **Bad:**
```yaml
guarantees:
  performance: "fast"  # Not measurable!
```

### Technology Alignment

✅ **Good:**
```yaml
# Web product inherits from web technology template
inherits_from: "pattern/agent/digital/web/react:v2.3"
```

❌ **Bad:**
```yaml
# Web product inherits from wrong technology
inherits_from: "pattern/agent/physical/robotics/ros2:v2.3"
```

---

## Architectural Placement

```
L0: Meta-Pattern (self-describing foundation)
    ↓
L1: Critical Patterns (13 universal capabilities)
    │   Classifications: L1C (Cognitive), L1I (Infrastructure), L1S (Security)
    ↓
L2: Reality Patterns (digital, physical, hybrid)
    ↓
L3: Technology Patterns (React, Django, ROS, Unity, PyTorch, etc.)
    ↓
L4: Products ← YOU ARE HERE
    │   Product contracts can require L1C cognitive capabilities:
    │   - "This product requires knowledge-representation"
    │   - "This product must implement value-system for ethics"
    │   - "This product needs experience-acquisition for learning"
    ↓ (implemented by)
L5: Solutions (actual code implementing the contracts)
```

**Products (L4)** define contracts that may include L1C cognitive requirements.  
**Products specify WHAT capabilities (including L1C) without specifying HOW.**  
Example: AGI assistant product contract requires L1C patterns; solutions implement them with actual PyTorch/TensorFlow code.

---

## Key Properties

### Contract-Focused

Products specify:
- **What** the system does (not how)
- **Inputs** required
- **Outputs** produced
- **Guarantees** provided

### Implementation-Agnostic

Same product can have:
- Multiple solutions (different implementations)
- Different technologies (as long as they match L3)
- Different vendors
- Different deployment models

### Reusable

Products enable:
- Standard interfaces across solutions
- Solution interchangeability
- Testing against contracts
- Documentation consistency

### Composable

Products can:
- Reference other products
- Delegate to components
- Aggregate outputs
- Form product families

---

## What This Means

**Products are not:**
- Code (that's L5)
- Technology-agnostic (they build on L3)
- Abstract patterns (that's L1/L2)

**Products are:**
- Reusable contract definitions
- Bridge between templates and implementations
- Foundation for multiple solutions
- Interface specifications with guarantees

---

## Bottom Line

**Products (L4)** define reusable contracts without implementation:
- **Contract:** Inputs, outputs, guarantees
- **Reusable:** Same contract, multiple solutions
- **Technology-aware:** Builds on L3 technology patterns
- **Composable:** Products reference other products

They enable:
- Solution interchangeability (swap implementations)
- Contract-based development (define then implement)
- Vendor independence (any solution that meets contract)
- Clear interfaces (exactly what to expect)

**Every Solution (L5) must implement a Product (L4) contract.**

Start with Products when you want to define what a component does before deciding how to implement it.

---

*For complete product definitions, see `product/*/product.yaml`*
