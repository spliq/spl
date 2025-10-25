# What are Reality Patterns?

Version: 2.3  
Owner: Spliq team  
License: Apache 2.0  
Status: Public explainer (publishable)  
Audience: Developers, architects, and engineers working across different realities

---

## Executive Summary

Reality Patterns (L2) specialize Critical Patterns for specific realities: **digital**, **physical**, and **hybrid**. They bridge the gap between universal capabilities (L1) and concrete technologies (L3) by adapting patterns to the constraints and affordances of different worlds.

---

## Definition

A **Reality Pattern** is a Layer 2 (L2) pattern that:

1. **Specializes a Critical Pattern** - Inherits from L1 (agent, validator, translator, etc.)
2. **Targets a specific reality** - Digital, physical, or hybrid
3. **Adds reality constraints** - File systems, sensors, networks, physics
4. **Enables cross-reality composition** - Patterns can work together across realities
5. **Prepares for technology** - Foundation for L3 technology-specific patterns

**Think of Reality Patterns as "reality adapters"** - they make universal patterns work in specific worlds.

---

## The L2 Test: What Makes a Pattern "Reality-Specific"?

A pattern belongs at L2 (Reality Patterns) only if it passes ALL these tests:

### 1. ✅ **Inherits from an L1 pattern**
   - Must specialize a Critical Pattern (L1 or L1C)
   - Cannot exist without L1 foundation
   - Example: `agent/digital` inherits from `agent` (L1)
   - Counter-example: A pattern with no L1 parent doesn't belong at L2

### 2. ✅ **Adds reality-specific constraints**
   - Introduces constraints unique to digital, physical, or hybrid worlds
   - Changes behavior based on reality characteristics
   - Example: `agent/physical` adds sensors, actuators, embodiment, physics
   - Counter-example: Adding React-specific code is L3 (technology), not L2

### 3. ✅ **Works across multiple technologies**
   - Still technology-agnostic within its reality
   - Can be implemented in any suitable technology for that reality
   - Example: `validator/digital` works with Python, JavaScript, Rust, etc.
   - Counter-example: `validator/digital/fastapi` is L3 (technology-specific)

### 4. ✅ **Addresses reality-specific challenges**
   - Solves problems unique to that reality
   - Example: `orchestrator/physical` handles energy constraints, synchronization delays
   - Example: `reality-bridge/hybrid` manages digital-physical state synchronization
   - Counter-example: HTTP routing is L3 (technology protocol), not L2

### 5. ✅ **Enables cross-reality composition**
   - Can work with patterns from other realities
   - Supports hybrid systems that span realities
   - Example: `translator/hybrid` converts between digital and physical representations
   - Counter-example: Patterns that can't interact across realities aren't L2

---

## Why Three Realities?

### Patterns That Don't Qualify as Separate Realities:

**Cloud vs on-premise**:
- ❌ Both are digital reality
- ❌ Deployment location is L3/L5 concern
- ✅ Use `pattern/*/digital` for both

**Virtual reality (VR)**:
- ❌ Fully digital (software rendering, digital state)
- ✅ Use `pattern/*/digital` with VR-specific L3 technologies

**Augmented reality (AR)**:
- ✅ Hybrid reality (digital overlays on physical world)
- ✅ Use `pattern/*/hybrid`

**Cyber-physical systems (CPS)**:
- ✅ Hybrid reality (tight digital-physical coupling)
- ✅ Use `pattern/*/hybrid`

**Edge computing**:
- ❌ Location/deployment strategy (L3/L5)
- ✅ Use appropriate reality (digital, physical, or hybrid)

### The Three Realities Are Fundamental:

1. **Digital**: Pure information (bits)
2. **Physical**: Pure matter (atoms)
3. **Hybrid**: Information + Matter (bits ↔ atoms)

These three cover ALL possible system realities. Adding more would create overlap or redundancy.

---

## The Three Realities

### 1. Digital Reality
**Where:** Software systems, cloud infrastructure, data processing  
**Characteristics:**
- Information-based (bits and bytes)
- Network communication
- Virtual state (memory, databases)
- Software-defined boundaries
- Instant replication

**Examples:**
- Web applications
- APIs and microservices
- Cloud functions
- Databases
- AI models

### 2. Physical Reality
**Where:** The material world with physical laws  
**Characteristics:**
- Embodied presence (actual location matters)
- Sensor-based perception
- Actuator-based action
- Energy and material constraints
- Irreversible actions

**Examples:**
- Robots and drones
- Manufacturing equipment
- Smart home devices
- Autonomous vehicles
- Medical devices

### 3. Hybrid Reality
**Where:** Systems spanning both digital and physical worlds  
**Characteristics:**
- Digital-physical interfaces
- State synchronization across realities
- Reality translation (bits ↔ atoms)
- Cross-reality workflows
- Mixed-reality interactions

**Examples:**
- Digital twins
- Augmented reality
- Smart buildings (BIM ↔ actual building)
- Industrial IoT
- Telemedicine platforms

---

## How Reality Patterns Work

Reality Patterns take universal Critical Patterns and adapt them:

```
Critical Pattern (L1)
    ↓ inherits_from
Reality Pattern (L2)
    ↓ adds reality context
```

### Example: Validator Pattern Across Realities

**L1 Critical Pattern:**
```yaml
id: "pattern/validator:v2.3"
# Universal validation capability
contract:
  goal: "Verify data meets constraints"
```

**L2 Digital Template:**
```yaml
id: "pattern/validator/digital:v2.3"
inherits_from: "pattern/validator:v2.3"
identity:
  reality: digital
  
# Adds digital-specific properties
digital_validation:
  mechanisms: ["schema_checking", "code_analysis", "runtime_monitoring"]
  constraints: ["file_formats", "api_contracts", "data_types"]
```

**L2 Physical Template:**
```yaml
id: "pattern/validator/physical:v2.3"
inherits_from: "pattern/validator:v2.3"
identity:
  reality: physical
  
# Adds physical-specific properties
physical_validation:
  mechanisms: ["sensor_verification", "measurement_checks", "safety_validation"]
  constraints: ["physical_laws", "safety_limits", "material_properties"]
```

**L2 Hybrid Template:**
```yaml
id: "pattern/validator/hybrid:v2.3"
inherits_from: "pattern/validator:v2.3"
identity:
  reality: hybrid
  
# Adds hybrid-specific properties
hybrid_validation:
  digital_component: { ... }
  physical_component: { ... }
  synchronization: ["state_consistency", "cross_reality_checks"]
```

---

## Digital Reality Patterns

### Key Characteristics

**Environment:** Software runtimes, operating systems, cloud platforms  
**State:** Memory, databases, caches  
**Communication:** APIs, events, messages  
**Resources:** CPU, memory, bandwidth, storage

### Example: Digital Agent Template

```yaml
id: "pattern/agent/digital:v2.3"
inherits_from: "pattern/agent:v2.3"
identity:
  reality: digital

digital_properties:
  execution_environment: "software_runtime"
  state_representation: "data_structures"
  interaction_mechanisms:
    - apis
    - events
    - message_queues
  resource_constraints:
    - memory_limits
    - cpu_allocation
    - network_bandwidth

contract:
  goal: "Autonomous digital behavior"
  inputs:
    - name: task
      type: object
      digital_format: json
  outputs:
    - name: result
      type: object
      digital_format: json
      
execution:
  digital_loop: "event_driven_processing"
  monitoring: ["cpu_usage", "memory_consumption", "api_latency"]

guarantees:
  digital_safety:
    - "Cannot access unauthorized files"
    - "Respects rate limits"
    - "Validates all inputs"
```

### Common Digital Templates

- **Agent/Digital** - Software agents, bots, services
- **Validator/Digital** - Schema validators, code analyzers
- **Translator/Digital** - Format converters, API adapters
- **Orchestrator/Digital** - Workflow engines, process managers
- **Entity/Digital** - Data models, database schemas

---

## Physical Reality Patterns

### Key Characteristics

**Environment:** The material world with physics  
**State:** Physical configuration, location, orientation  
**Communication:** Sensors, actuators, physical signals  
**Resources:** Energy, materials, space, time

### Example: Physical Agent Template

```yaml
id: "pattern/agent/physical:v2.3"
inherits_from: "pattern/agent:v2.3"
identity:
  reality: physical

physical_properties:
  embodiment: "physical_form"
  perception:
    sensors: ["cameras", "lidar", "imu", "tactile"]
  actuation:
    actuators: ["motors", "servos", "grippers"]
  resource_constraints:
    - power_consumption
    - weight_limits
    - spatial_footprint
    - thermal_dissipation

contract:
  goal: "Autonomous physical behavior"
  inputs:
    - name: task
      type: object
      physical_context: "environmental_state"
  outputs:
    - name: action
      type: object
      physical_result: "state_change"

execution:
  physical_loop: "sense_plan_act"
  monitoring: ["battery_level", "motor_current", "sensor_health"]

guarantees:
  physical_safety:
    - "Respects proximity limits"
    - "Force limiting enabled"
    - "Emergency stop accessible"
    - "Collision detection active"
```

### Common Physical Templates

- **Agent/Physical** - Robots, drones, autonomous vehicles
- **Validator/Physical** - Quality inspection, safety verification
- **Translator/Physical** - Sensor fusion, command interpretation
- **Monitor/Physical** - Environmental monitoring, equipment tracking
- **Reality-Bridge/Physical** - Physical-to-digital interfaces

---

## Hybrid Reality Patterns

### Key Characteristics

**Environment:** Spans both digital and physical worlds  
**State:** Synchronized across realities  
**Communication:** Digital-physical translation  
**Resources:** Both digital and physical constraints apply

### Example: Hybrid Reality-Bridge Template

```yaml
id: "pattern/reality-bridge/hybrid:v2.3"
inherits_from: "pattern/reality-bridge:v2.3"
identity:
  reality: hybrid

hybrid_properties:
  digital_component:
    representation: "3d_model"
    state: "virtual_twin"
    interfaces: ["rest_api", "websocket"]
    
  physical_component:
    embodiment: "sensor_network"
    state: "actual_measurements"
    interfaces: ["modbus", "mqtt"]
    
  synchronization:
    mechanisms:
      - "real_time_state_sync"
      - "event_propagation"
      - "conflict_resolution"
    frequency: "100hz"
    latency_limit: "10ms"

contract:
  goal: "Maintain consistency between digital and physical representations"
  inputs:
    - name: digital_state
      type: object
      source: digital_twin
    - name: physical_measurements
      type: object
      source: sensor_network
  outputs:
    - name: synchronized_state
      type: object
      truth_score: number  # Fidelity measure

execution:
  hybrid_loop: "measure_compare_sync_actuate"
  monitoring:
    - "synchronization_lag"
    - "state_divergence"
    - "fidelity_score"

guarantees:
  hybrid_safety:
    - "Digital changes validated before physical application"
    - "Physical limits enforced in digital model"
    - "Safe fallback on sync failure"
```

### Common Hybrid Templates

- **Reality-Bridge/Hybrid** - Digital twin synchronization
- **Translator/Hybrid** - Digital↔Physical translation
- **Agent/Hybrid** - AR/VR agents, cyber-physical systems
- **Orchestrator/Hybrid** - Smart building controllers
- **Monitor/Hybrid** - Industrial IoT monitoring

---

## Cross-Reality Patterns

Some use cases require patterns to work across multiple realities:

### Digital-to-Physical Translation

```yaml
# Example: Command translator
id: "pattern/translator/digital-to-physical:v2.3"

translation_flow:
  input: "Digital command (JSON)"
  process:
    - "Parse digital command"
    - "Validate safety constraints"
    - "Map to physical actuator signals"
    - "Apply physical limits"
  output: "Physical actuation (motor commands)"

safety:
  - "Digital commands cannot exceed physical limits"
  - "Emergency stop overrides all translations"
```

### Physical-to-Digital Translation

```yaml
# Example: Sensor data translator
id: "pattern/translator/physical-to-digital:v2.3"

translation_flow:
  input: "Physical measurements (sensor readings)"
  process:
    - "Read sensor values"
    - "Apply calibration"
    - "Filter noise"
    - "Convert to digital format"
  output: "Digital representation (JSON with truth scores)"

quality:
  - "Confidence intervals on all measurements"
  - "Outlier detection"
  - "Sensor health monitoring"
```

---

## Reality Pattern Composition

Reality Patterns can be composed to create powerful cross-reality systems:

### Example: Smart Factory Orchestrator

```yaml
id: "my-smart-factory-orchestrator:v2.3"
inherits_from: "pattern/orchestrator/hybrid:v2.3"

uses:
  # Digital components
  - pattern/validator/digital:v2.3  # Validate production plans
  - pattern/agent/digital:v2.3      # Optimization algorithms
  
  # Physical components
  - pattern/monitor/physical:v2.3   # Equipment monitoring
  - pattern/agent/physical:v2.3     # Robot controllers
  
  # Hybrid components
  - pattern/reality-bridge/hybrid:v2.3  # Digital twin sync
  - pattern/translator/hybrid:v2.3      # Command translation

workflow:
  - "Optimize production plan (digital)"
  - "Validate against constraints (digital)"
  - "Translate to robot commands (hybrid)"
  - "Execute on factory floor (physical)"
  - "Monitor execution (physical)"
  - "Update digital twin (hybrid)"
  - "Learn and re-optimize (digital)"
```

---

## Key Properties

### Reality-Specific Constraints

Each reality adds specific constraints:

**Digital:**
- File formats and schemas
- API contracts
- Network protocols
- Data types

**Physical:**
- Physical laws (gravity, friction, etc.)
- Safety limits
- Material properties
- Energy constraints

**Hybrid:**
- Synchronization requirements
- Cross-reality consistency
- Translation fidelity
- Latency limits

### Reality-Specific Affordances

Each reality provides specific capabilities:

**Digital:**
- Instant replication
- Perfect memory
- Infinite parallelism (in theory)
- Reversible operations

**Physical:**
- Direct environmental interaction
- Physical presence
- Tangible output
- Real-world sensing

**Hybrid:**
- Best of both worlds
- Cross-reality coordination
- Mixed-reality experiences
- Digital-physical feedback loops

---

## Architectural Placement

```
L0: Meta-Pattern (self-describing foundation)
    ↓
L1: Critical Patterns (13 universal capabilities)
    │   Classifications: L1C (Cognitive), L1I (Infrastructure), L1S (Security)
    ↓ (ALL L1 patterns specialize to realities)
L2: Reality Patterns ← YOU ARE HERE
    │   Examples for L1C patterns:
    │   - knowledge-representation/digital (AI knowledge bases)
    │   - value-system/physical (robotic ethics systems)
    │   - experience-acquisition/hybrid (AR/VR learning)
    │   
    │   Examples for regular L1 patterns:
    │   - agent/digital (web agents)
    │   - validator/physical (quality inspection robots)
    │   - translator/hybrid (digital twin interfaces)
    ↓
L3: Technology Patterns (React, ROS, Django, Unity, PyTorch, etc.)
    ↓
L4: Products (contract definitions)
    ↓
L5: Solutions (implementations with code)
```

**Reality Patterns (L2)** specialize ANY L1 pattern for digital, physical, or hybrid realities.  
**L1C patterns flow through L2 just like other L1 patterns.**  
Example flow: `knowledge-representation` (L1C) → `knowledge-representation/digital` (L2) → `knowledge-representation/digital/pytorch` (L3)

---

## What This Means

**Reality Patterns are not:**
- Technology-specific (that's L3)
- Implementations (that's L5)
- Optional (required bridge from L1 to L3)

**Reality Patterns are:**
- Reality adapters for Critical Patterns
- The bridge between universal and concrete
- Foundation for cross-reality systems
- Source of reality-specific constraints and affordances

---

## Bottom Line

**Reality Patterns (L2)** adapt universal Critical Patterns to work in:
- **Digital** reality (software, data, networks)
- **Physical** reality (robots, sensors, actuators)
- **Hybrid** reality (digital twins, AR/VR, IoT)

They enable:
- Cross-reality composition
- Reality-appropriate constraints
- Technology-independent design
- Verifiable cross-reality systems

**Every technology-specific pattern (L3) must inherit from a Reality Pattern (L2).**

Start with Reality Patterns when you need to work across digital, physical, or hybrid worlds while keeping technology options open.

---

*For complete specifications, see `patterns/*/digital|physical|hybrid/v2.3/*.yaml`*
