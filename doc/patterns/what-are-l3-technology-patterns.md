# What are Technology Patterns?

Version: 2.3  
Owner: SPLiQ team  
License: Apache 2.0  
Status: Public explainer (publishable)  
Audience: Developers implementing SPL patterns with specific technologies

---

## Executive Summary

Technology Patterns (L3) specialize Reality Patterns for specific technologies and platforms. They bridge abstract reality-aware patterns (L2) with concrete implementations by adding technology-specific interfaces, constraints, and best practices.

---

## Definition

A **Technology Pattern** is a Layer 3 (L3) pattern that:

1. **Specializes a Reality Pattern** - Inherits from L2 (digital/physical/hybrid)
2. **Targets specific technology** - React, Django, ROS, Arduino, Unity, etc.
3. **Adds technology constraints** - Framework APIs, platform limitations, best practices
4. **Provides implementation guidance** - How to actually build this in the technology
5. **Prepares for products** - Foundation for L4 product contracts

**Think of Technology Patterns as "technology adapters"** - they make reality-aware patterns work with specific frameworks and platforms.

---

## The L3 Test: What Makes a Pattern "Technology-Specific"?

A pattern belongs at L3 (Technology Patterns) only if it passes ALL these tests:

### 1. ✅ **Inherits from an L2 reality pattern**
   - Must specialize a Reality Pattern (digital, physical, or hybrid)
   - Cannot exist without L2 foundation
   - Example: `agent/digital/react` inherits from `agent/digital` (L2)
   - Counter-example: A pattern with no L2 parent doesn't belong at L3

### 2. ✅ **Requires specific technology/framework**
   - Tied to a concrete technology, language, or platform
   - Uses technology-specific APIs and idioms
   - Example: `agent/digital/react` requires React framework and JSX
   - Counter-example: "web agent" works with any web framework (that's L2, not L3)

### 3. ✅ **Provides implementation guidance**
   - Explains HOW to implement in this specific technology
   - Includes framework-specific patterns and best practices
   - Example: `validator/digital/fastapi` shows how to use FastAPI's validation decorators
   - Counter-example: Generic validation rules without tech details (that's L2)

### 4. ✅ **Still defines patterns, not products**
   - Describes technology approach, not specific product contracts
   - Reusable across multiple products using that technology
   - Example: `orchestrator/physical/ros2` applies to any ROS2 orchestration
   - Counter-example: "smart home controller using ROS2" is L4 (product)

### 5. ✅ **Technology can change without changing L1/L2**
   - Swapping technologies means changing L3, not architecture
   - L1/L2 patterns remain stable when technology evolves
   - Example: Switching from React to Vue changes L3, not the `agent/digital` L2 pattern
   - Counter-example: If changing tech requires changing L1/L2, it's not properly layered

---

## Why These Technologies?

### What Qualifies as L3 Technology:

**Frameworks and platforms**:
- ✅ React, Vue, Angular, Svelte (web UI frameworks)
- ✅ Django, FastAPI, Express (backend frameworks)
- ✅ ROS, ROS2 (robotics platforms)
- ✅ PyTorch, TensorFlow (ML frameworks)
- ✅ Unity, Unreal (game/AR/VR engines)

**Languages alone don't define L3**:
- ❌ "Python pattern" is too broad (language ≠ technology)
- ✅ "FastAPI pattern" is L3 (Python + specific framework)
- ❌ "JavaScript pattern" is too broad
- ✅ "React pattern" is L3 (JavaScript + specific framework)

**Infrastructure is NOT L3**:
- ❌ Kubernetes, Docker (deployment tech → L5 solutions)
- ❌ AWS, Azure (cloud platforms → L5 deployment)
- ✅ Use L3 for application frameworks, L5 for infrastructure

**Protocols alone are NOT L3**:
- ❌ HTTP, REST, GraphQL (protocols → can be L2 or L4 contracts)
- ✅ "FastAPI REST pattern" combines framework + protocol (L3)

### Technology Patterns vs Reality Patterns:

| Aspect | L2 (Reality) | L3 (Technology) |
|--------|-------------|-----------------|
| Scope | All digital/physical/hybrid | Specific framework |
| Example | `agent/digital` | `agent/digital/react` |
| Language | Any language | Specific language+framework |
| Changeability | Stable | Changes with tech evolution |
| Reusability | Across all digital tech | Within React ecosystem |

---

## Why Technology Patterns Matter

### The Problem Without L3

```
L2: "I need a digital web agent"
L5: "Here's React code!"

❌ Gap: How do I translate "digital agent" concepts to React specifics?
```

### The Solution With L3

```
L2: Reality Template (digital agent)
    ↓
L3: Technology Pattern (React agent)
    ↓ provides technology-specific guidance
L5: Solution (actual React implementation)

✓ Clear path from abstract to concrete
```

---

## How Technology Patterns Work

Technology Patterns add technology-specific details to reality-aware patterns:

```
Reality Template (L2)
    ↓ inherits_from
Technology Pattern (L3)
    ↓ adds technology specifics
```

### Example: Web Application Agent

**L2 Reality Template:**
```yaml
id: "pattern/agent/digital:v2.3"
# Reality: digital
# Constraints: software runtime, network communication
```

**L3 Technology Pattern:**
```yaml
id: "pattern/agent/digital/web:v2.3"
inherits_from: "pattern/agent/digital:v2.3"
identity:
  reality: digital
  technology: web
  
# Adds web-specific properties
web_specific:
  client_side:
    - "Browser APIs"
    - "DOM manipulation"
    - "Client-side routing"
  server_side:
    - "HTTP request handling"
    - "Session management"
    - "API implementation"
  communication:
    - "REST"
    - "GraphQL"
    - "WebSockets"
```

**L3 Framework-Specific Template:**
```yaml
id: "pattern/agent/digital/web/react:v2.3"
inherits_from: "pattern/agent/digital/web:v2.3"
identity:
  technology: "react"
  
# Adds React-specific properties
react_specific:
  component_model: "functional_with_hooks"
  state_management: ["useState", "useReducer", "Context"]
  lifecycle: ["useEffect", "useLayoutEffect"]
  patterns:
    - "component_composition"
    - "hooks_patterns"
    - "context_providers"
```

---

## Categories of Technology Patterns

### Digital Technology Patterns

#### Web Frameworks
- **React** - Component-based UI
- **Vue** - Progressive framework
- **Angular** - Full-featured framework
- **Svelte** - Compile-time framework
- **Next.js** - React with SSR
- **Vite** - Modern build tool

#### Backend Frameworks
- **Django** - Python web framework
- **FastAPI** - Modern Python API
- **Express** - Node.js web framework
- **Spring Boot** - Java enterprise
- **Rails** - Ruby web framework

#### Database Systems
- **PostgreSQL** - Relational database
- **MongoDB** - Document database
- **Redis** - Key-value store
- **Neo4j** - Graph database

#### AI/ML Frameworks
- **PyTorch** - Deep learning
- **TensorFlow** - ML platform
- **Scikit-learn** - Classical ML
- **Hugging Face** - LLM platform

### Physical Technology Patterns

#### Robotics Platforms
- **ROS** (Robot Operating System)
- **ROS2** - Next-gen ROS
- **Arduino** - Microcontroller platform
- **Raspberry Pi** - Single-board computer

#### Industrial Systems
- **PLC** (Programmable Logic Controllers)
- **SCADA** - Supervisory control
- **Modbus** - Industrial protocol
- **OPC-UA** - Industrial interoperability

#### IoT Platforms
- **MQTT** - IoT messaging
- **Zigbee** - Low-power wireless
- **LoRaWAN** - Long-range network
- **Thread** - Mesh networking

### Hybrid Technology Patterns

#### AR/VR Platforms
- **Unity** - Game engine for AR/VR
- **Unreal Engine** - High-fidelity 3D
- **ARKit** - Apple AR
- **ARCore** - Google AR

#### Digital Twin Platforms
- **Azure Digital Twins**
- **AWS IoT TwinMaker**
- **NVIDIA Omniverse**

---

## Example Technology Patterns

### Digital/Web/React Agent Template

```yaml
id: "pattern/agent/digital/web/react:v2.3"
inherits_from: "pattern/agent/digital/web:v2.3"
identity:
  reality: digital
  technology: react
  
react_agent_properties:
  component_structure:
    - "AgentProvider (context)"
    - "AgentController (logic)"
    - "AgentView (UI)"
    
  state_management:
    agent_state: "useReducer hook"
    side_effects: "useEffect for async actions"
    context: "AgentContext for global state"
    
  lifecycle:
    initialization: "useEffect with empty deps"
    cleanup: "return cleanup function"
    updates: "useEffect with dependencies"
    
  api_integration:
    data_fetching: "React Query or SWR"
    websockets: "useWebSocket hook"
    error_handling: "Error Boundaries"

contract:
  goal: "Autonomous behavior in React applications"
  inputs:
    - name: task
      type: ReactProps
      structure: "{ task: string, context: object }"
  outputs:
    - name: action
      type: ReactComponent
      structure: "JSX with event handlers"

execution:
  react_loop:
    - "Render component"
    - "Handle user events"
    - "Update state via reducer"
    - "Trigger side effects"
    - "Re-render on state change"
    
  best_practices:
    - "Use functional components"
    - "Memoize expensive computations"
    - "Implement proper cleanup"
    - "Handle loading and error states"

guarantees:
  react_safety:
    - "No memory leaks (cleanup subscriptions)"
    - "Proper error boundaries"
    - "Accessible UI components"
    - "Performance monitoring"

example_usage: |
  import { AgentProvider, useAgent } from '@spl/react-agent';
  
  function MyApp() {
    return (
      <AgentProvider config={{ ... }}>
        <AgentComponent />
      </AgentProvider>
    );
  }
  
  function AgentComponent() {
    const { execute, status, result } = useAgent();
    
    return (
      <div>
        <button onClick={() => execute(task)}>
          Run Agent
        </button>
        {status === 'loading' && <Spinner />}
        {result && <Result data={result} />}
      </div>
    );
  }
```

### Physical/Robotics/ROS Agent Template

```yaml
id: "pattern/agent/physical/robotics/ros2:v2.3"
inherits_from: "pattern/agent/physical/robotics:v2.3"
identity:
  reality: physical
  technology: ros2

ros2_agent_properties:
  node_structure:
    - "rclpy.Node subclass"
    - "Publishers for actions"
    - "Subscribers for sensors"
    - "Services for queries"
    - "Action servers for tasks"
    
  communication:
    topics: "sensor_data, commands, state"
    services: "query_state, set_parameters"
    actions: "execute_task (with feedback)"
    
  lifecycle:
    initialization: "on_configure"
    activation: "on_activate"
    execution: "timer_callback loop"
    cleanup: "on_cleanup"
    
  best_practices:
    - "Use lifecycle nodes"
    - "Implement QoS profiles"
    - "Handle node failure gracefully"
    - "Log to ROS logging system"

contract:
  goal: "Autonomous robotic behavior via ROS2"
  inputs:
    - name: task
      type: Action
      ros_type: "my_interfaces/ExecuteTask"
  outputs:
    - name: result
      type: ActionResult
      ros_type: "my_interfaces/ExecuteTaskResult"

execution:
  ros2_loop:
    - "Receive sensor data via subscribers"
    - "Process in timer callback"
    - "Publish commands to actuators"
    - "Send action feedback"
    - "Return result on completion"
    
  monitoring:
    - "Node health via lifecycle"
    - "Topic statistics"
    - "Tf tree validation"

guarantees:
  ros2_safety:
    - "Emergency stop via service"
    - "Watchdog for node health"
    - "Safe state on failure"
    - "Proper tf broadcasting"

example_usage: |
  import rclpy
  from rclpy.node import Node
  from rclpy.action import ActionServer
  
  class AgentNode(Node):
      def __init__(self):
          super().__init__('agent_node')
          self._action_server = ActionServer(
              self, ExecuteTask, 'execute_task',
              self.execute_callback
          )
          
      def execute_callback(self, goal_handle):
          # Execute agent logic
          result = ExecuteTaskResult()
          result.success = True
          result.truth_score = 0.95
          return result
```

### Hybrid/AR/Unity Reality-Bridge Template

```yaml
id: "pattern/reality-bridge/hybrid/ar/unity:v2.3"
inherits_from: "pattern/reality-bridge/hybrid/ar:v2.3"
identity:
  reality: hybrid
  technology: unity

unity_bridge_properties:
  scene_structure:
    - "ARSession (AR Foundation)"
    - "ARPlaneManager (surface detection)"
    - "ARRaycastManager (interaction)"
    - "NetworkManager (digital sync)"
    
  synchronization:
    physical_tracking: "ARKit/ARCore pose tracking"
    digital_state: "Networked game objects"
    update_rate: "60fps for AR, 10fps for network"
    
  unity_specifics:
    scripting: "C# MonoBehaviour"
    rendering: "URP (Universal Render Pipeline)"
    physics: "Unity Physics for collision"
    networking: "Mirror or Netcode for GameObjects"

contract:
  goal: "Sync digital content with physical AR environment"
  inputs:
    - name: physical_environment
      type: ARWorldMap
      source: "AR tracking"
    - name: digital_state
      type: NetworkedState
      source: "Server sync"
  outputs:
    - name: rendered_scene
      type: ARScene
      result: "Mixed reality view"

execution:
  unity_loop:
    - "Update() - Handle AR tracking"
    - "FixedUpdate() - Physics simulation"
    - "LateUpdate() - Sync digital state"
    - "OnRenderObject() - Render AR content"
    
  best_practices:
    - "Use object pooling for performance"
    - "Implement occlusion"
    - "Handle AR session interruptions"
    - "Optimize for mobile performance"

guarantees:
  unity_safety:
    - "Frame rate > 30fps (motion sickness prevention)"
    - "Graceful degradation on tracking loss"
    - "User warnings for safety hazards"
    - "Privacy indicators for camera use"

example_usage: |
  using UnityEngine;
  using UnityEngine.XR.ARFoundation;
  
  public class ARBridge : MonoBehaviour
  {
      ARRaycastManager raycastManager;
      NetworkManager networkManager;
      
      void Update() {
          // Track physical environment
          var hits = new List<ARRaycastHit>();
          raycastManager.Raycast(screenPoint, hits);
          
          // Sync with digital state
          networkManager.SyncState(hits);
          
          // Render mixed reality
          RenderARContent();
      }
  }
```

---

## Technology Pattern Patterns

### Common Patterns Across Technologies

#### 1. Configuration Management
```yaml
configuration:
  environment_variables: "Technology-specific env vars"
  config_files: "Technology-specific config format"
  defaults: "Sensible defaults for the technology"
```

#### 2. Error Handling
```yaml
error_handling:
  exceptions: "Technology-specific exception types"
  logging: "Technology logging framework"
  recovery: "Technology-appropriate recovery strategies"
```

#### 3. Testing
```yaml
testing:
  unit_tests: "Technology test framework (Jest, pytest, etc.)"
  integration_tests: "Technology integration patterns"
  mocking: "Technology mocking libraries"
```

#### 4. Deployment
```yaml
deployment:
  packaging: "Technology package format (npm, pip, Docker, etc.)"
  dependencies: "Technology dependency management"
  runtime: "Technology runtime requirements"
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
L3: Technology Patterns ← YOU ARE HERE
    │   Examples for L1C cognitive patterns:
    │   - knowledge-representation/digital/pytorch (AI knowledge graphs)
    │   - experience-acquisition/digital/tensorflow (ML training)
    │   - value-system/physical/ros2 (robot ethics)
    │   
    │   Examples for regular L1 patterns:
    │   - agent/digital/react (web UI agents)
    │   - validator/digital/fastapi (API validation)
    │   - orchestrator/physical/ros2 (robot coordination)
    ↓
L4: Products (contract definitions, no code)
    ↓
L5: Solutions (implementations with actual code)
```

**Technology Patterns (L3)** specialize L2 Reality Patterns for specific technologies.  
**L1C patterns are implemented with concrete technologies just like other L1 patterns.**  
Example: `knowledge-representation/digital/pytorch` uses PyTorch for AI knowledge representation.

---

## Key Properties

### Technology-Specific

Each template adds:
- **Framework APIs** - How to use the technology
- **Best practices** - Idiomatic patterns for the technology
- **Constraints** - Technology limitations
- **Tooling** - Build tools, testing frameworks, debuggers

### Implementation-Ready

Technology Patterns provide:
- **Code patterns** - Example usage
- **API guidance** - How to structure code
- **Integration points** - How to connect components
- **Testing strategies** - How to verify behavior

### Composable

Technology Patterns can be combined:
```yaml
# React frontend + Django backend
web_app:
  frontend:
    inherits_from: "pattern/agent/digital/web/react:v2.3"
  backend:
    inherits_from: "pattern/orchestrator/digital/api/django:v2.3"
  communication:
    inherits_from: "pattern/translator/digital/rest:v2.3"
```

---

## What This Means

**Technology Patterns are not:**
- Implementations (that's L5)
- Product definitions (that's L4)
- Reality-agnostic (they build on L2)

**Technology Patterns are:**
- Technology-specific guidance for implementing patterns
- Bridge between abstract patterns and concrete code
- Source of best practices and constraints
- Foundation for product contracts

---

## Bottom Line

**Technology Patterns (L3)** specialize Reality Patterns for specific technologies:
- **Web:** React, Vue, Django, FastAPI, etc.
- **Robotics:** ROS, ROS2, Arduino, PLC
- **AR/VR:** Unity, Unreal, ARKit, ARCore
- **Database:** PostgreSQL, MongoDB, Redis
- **AI/ML:** PyTorch, TensorFlow, Hugging Face

They enable:
- Technology-appropriate implementations
- Best practices enforcement
- Clear implementation guidance
- Technology interoperability

**Every Product (L4) should inherit from a Technology Pattern (L3).**

Start with Technology Patterns when you know what technology stack you're using and need specific implementation guidance.

---

*For complete specifications, see `patterns/*/*/<technology>/v2.3/*.yaml`*
