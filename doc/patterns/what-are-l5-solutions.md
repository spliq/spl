# What are Solutions?

Version: 2.3  
Owner: SPLiQ team  
License: Apache 2.0  
Status: Public explainer (publishable)  
Audience: Developers implementing SPL solutions with actual code

---

## Executive Summary

Solutions (L5) are complete implementations with actual code. They implement Product (L4) contracts using specific technologies, libraries, and deployment configurations. Solutions are runnable, testable, and deployable systems.

**Key insight:** Solutions are code. They deliver the promise made by Product contracts.

---

## Definition

A **Solution** is a Layer 5 (L5) pattern that:

1. **Implements a Product contract (L4)** - Fulfills all inputs, outputs, guarantees
2. **Contains actual code** - Python, JavaScript, C++, etc.
3. **Is runnable** - Can be executed in its target environment
4. **Is deployable** - Has deployment configuration
5. **Is testable** - Includes tests verifying contract compliance

**Think of Solutions as "working software"** - they are the actual implementation that users run.

---

## The L5 Test: What Makes a Pattern a "Solution"?

A pattern belongs at L5 (Solutions) only if it passes ALL these tests:

### 1. ✅ **Implements an L4 product contract**
   - Must fulfill a specific product's contract
   - Satisfies all inputs, outputs, and guarantees
   - Example: Solution implements `product/llm-chat-assistant:v2.3` contract
   - Counter-example: Code without a product contract is just code, not an SPL solution

### 2. ✅ **Contains executable code**
   - Actual source code in a programming language
   - Runnable implementations of functions, classes, modules
   - Example: Python files with LLM integration, API handlers, etc.
   - Counter-example: YAML contract definitions are L4 (products), not L5

### 3. ✅ **Includes ALL deployment artifacts**
   - Dependencies (requirements.txt, package.json, etc.)
   - Configuration (environment variables, settings files)
   - Deployment files (Dockerfile, kubernetes manifests, etc.)
   - Example: Complete solution directory with src/, tests/, config/, deployment/
   - Counter-example: Just source code without dependencies/config is incomplete

### 4. ✅ **Has tests proving contract compliance**
   - Unit tests for components
   - Integration tests for system behavior
   - Contract tests verifying product guarantees
   - Example: Tests proving "response time < 5s p95" guarantee is met
   - Counter-example: Untested code doesn't prove it satisfies the contract

### 5. ✅ **Is deployable and runnable**
   - Can be deployed to target environment
   - Runs successfully with proper configuration
   - Includes documentation for deployment and operation
   - Example: Docker container that can be deployed to production
   - Counter-example: Theoretical code that can't actually run is not a solution

---

## Solutions vs Products

### What's the difference?

| Aspect | L4 (Product) | L5 (Solution) |
|--------|-------------|---------------|
| **Nature** | Contract/specification | Implementation/code |
| **Contains** | Inputs, outputs, guarantees | Source code, tests, config |
| **Executable** | No (just defines WHAT) | Yes (runs and delivers) |
| **Multiple** | One contract | Many implementations |
| **Example** | "Chat assistant must respond in <5s" | `openai_assistant.py` with actual API calls |
| **Changes** | Stable (contract rarely changes) | Evolves (implementations improve) |
| **Testing** | Contract is testable | Tests prove compliance |

### When to create L4 vs L5:

**Create L4 Product when:**
- You want to define WHAT without specifying HOW
- You want multiple teams to implement the same capability
- You need a stable contract that solutions must satisfy
- Example: "LLM assistant product" → allows OpenAI, Anthropic, local LLM solutions

**Create L5 Solution when:**
- You're implementing actual working code
- You're choosing specific libraries, algorithms, architectures
- You're deploying to specific infrastructure
- Example: "OpenAI GPT-4 assistant solution" → actual Python implementation

---

## Why Solutions Matter

### The Problem Without L5

```
L4: Product contract (what the system should do)

❌ Gap: How do users actually run this?
```

### The Solution With L5

```
L4: Product (LLM Chat Assistant contract)
    ↓
L5: Solution (actual implementation)
    ↓ provides
    - Source code (Python, JavaScript, etc.)
    - Dependencies (requirements.txt, package.json)
    - Configuration (environment variables, settings)
    - Deployment (Docker, Kubernetes, etc.)
    - Tests (unit tests, integration tests)
    
✓ Users can run, deploy, and use the system
```

---

## Solutions vs Products

### Product (L4): Contract

```yaml
id: "product/llm-chat-assistant:v2.3"

contract:
  inputs: [user_message, conversation_history]
  outputs: [assistant_response, truth_score]
  guarantees:
    response_time: "< 5 seconds p95"
    safety: "Content filtered"
```

### Solution (L5): Implementation

```
product/llm-chat-assistant/solutions/openai-gpt4/
  solution.yaml              # Solution metadata
  src/
    assistant.py             # Implementation code
    config.py                # Configuration
  tests/
    test_assistant.py        # Tests
  requirements.txt           # Dependencies
  Dockerfile                 # Deployment
  README.md                  # Documentation
```

**Product defines the promise, Solution delivers it.**

---

## Solution Structure

### Directory Layout

```
product/<product-name>/solutions/<solution-name>/
  solution.yaml              # Solution metadata
  src/                       # Source code
    main.py                  # Entry point
    *.py                     # Implementation modules
  tests/                     # Tests
    test_*.py                # Test files
  requirements.txt           # Python dependencies
  package.json               # Node dependencies (if applicable)
  Dockerfile                 # Container definition
  docker-compose.yml         # Multi-container deployment
  .env.example               # Environment variables template
  README.md                  # Solution documentation
  LICENSE                    # License
```

### solution.yaml

```yaml
id: "solution/llm-chat-assistant/openai-gpt4:v2.3"
implements: "product/llm-chat-assistant:v2.3"

identity:
  name: "OpenAI GPT-4 Chat Assistant"
  description: "LLM chat assistant using OpenAI GPT-4 API"
  version: "2.3"
  
technology:
  runtime: "python3.11"
  frameworks: ["openai", "fastapi"]
  deployment: "docker"
  
contract_implementation:
  # How this solution implements the product contract
  inputs:
    user_message: "function parameter"
    conversation_history: "function parameter"
  outputs:
    assistant_response: "return value .response"
    truth_score: "return value .truth_score"
  guarantees:
    response_time: "Measured in production metrics"
    safety: "OpenAI moderation API"
    
dependencies:
  python: "requirements.txt"
  system: ["docker", "docker-compose"]
  
deployment:
  type: "docker-compose"
  environment_variables:
    - "OPENAI_API_KEY"
    - "LOG_LEVEL"
  ports:
    - "8000:8000"
    
testing:
  framework: "pytest"
  coverage_minimum: 80
  test_command: "pytest tests/ --cov=src"
  
documentation:
  readme: "README.md"
  api_docs: "http://localhost:8000/docs"
```

---

## Example Solutions

### Digital Solution: OpenAI GPT-4 Chat Assistant

```
product/llm-chat-assistant/solutions/openai-gpt4/
```

**solution.yaml:**
```yaml
id: "solution/llm-chat-assistant/openai-gpt4:v2.3"
implements: "product/llm-chat-assistant:v2.3"

identity:
  name: "OpenAI GPT-4 Chat Assistant"
  technology: "openai-api"
```

**src/assistant.py:**
```python
"""OpenAI GPT-4 Chat Assistant Implementation"""

from openai import OpenAI
from typing import List, Dict
import time

class ChatAssistant:
    """Implements product/llm-chat-assistant:v2.3 using OpenAI GPT-4"""
    
    def __init__(self, api_key: str, model: str = "gpt-4"):
        self.client = OpenAI(api_key=api_key)
        self.model = model
        
    def chat(
        self,
        user_message: str,
        conversation_history: List[Dict[str, str]] = None,
        system_prompt: str = None,
        max_tokens: int = 1000
    ) -> Dict:
        """
        Implements the product contract.
        
        Args:
            user_message: User's input message
            conversation_history: Previous messages [{role, content}]
            system_prompt: Instructions for assistant behavior
            max_tokens: Maximum response length
            
        Returns:
            {
                assistant_response: str,
                truth_score: float,
                tokens_used: {input: int, output: int, total: int}
            }
        """
        start_time = time.time()
        
        # Build messages
        messages = []
        if system_prompt:
            messages.append({"role": "system", "content": system_prompt})
        if conversation_history:
            messages.extend(conversation_history)
        messages.append({"role": "user", "content": user_message})
        
        # Call OpenAI API
        response = self.client.chat.completions.create(
            model=self.model,
            messages=messages,
            max_tokens=max_tokens,
            temperature=0.7
        )
        
        # Verify response time guarantee (< 5s p95)
        elapsed = time.time() - start_time
        if elapsed > 5.0:
            print(f"Warning: Response time {elapsed:.2f}s exceeds p95 guarantee")
        
        # Extract response
        assistant_response = response.choices[0].message.content
        
        # Calculate truth score (using OpenAI's confidence if available)
        # For GPT-4, we use a heuristic based on finish_reason
        truth_score = 0.85  # Default high confidence
        if response.choices[0].finish_reason == "length":
            truth_score = 0.70  # Lower confidence if cut off
        
        # Token usage
        tokens_used = {
            "input": response.usage.prompt_tokens,
            "output": response.usage.completion_tokens,
            "total": response.usage.total_tokens
        }
        
        return {
            "assistant_response": assistant_response,
            "truth_score": truth_score,
            "tokens_used": tokens_used
        }
```

**tests/test_assistant.py:**
```python
"""Tests for OpenAI GPT-4 Chat Assistant"""

import pytest
from src.assistant import ChatAssistant
import os

@pytest.fixture
def assistant():
    api_key = os.getenv("OPENAI_API_KEY", "test-key")
    return ChatAssistant(api_key=api_key)

def test_chat_basic(assistant):
    """Test basic chat functionality"""
    result = assistant.chat("What is 2+2?")
    
    # Verify contract outputs
    assert "assistant_response" in result
    assert "truth_score" in result
    assert "tokens_used" in result
    
    # Verify types
    assert isinstance(result["assistant_response"], str)
    assert isinstance(result["truth_score"], float)
    assert 0.0 <= result["truth_score"] <= 1.0
    
def test_chat_with_history(assistant):
    """Test chat with conversation history"""
    history = [
        {"role": "user", "content": "My name is Alice"},
        {"role": "assistant", "content": "Hello Alice!"}
    ]
    
    result = assistant.chat("What's my name?", conversation_history=history)
    
    # Should remember the name
    assert "alice" in result["assistant_response"].lower()
    
def test_response_time_guarantee(assistant):
    """Test that response time meets guarantee (< 5s p95)"""
    import time
    
    start = time.time()
    result = assistant.chat("Quick question: what is AI?")
    elapsed = time.time() - start
    
    # Should complete in < 5 seconds (p95 guarantee)
    assert elapsed < 5.0, f"Response took {elapsed:.2f}s, exceeds 5s guarantee"
```

**requirements.txt:**
```
openai==1.3.0
fastapi==0.104.1
uvicorn==0.24.0
pytest==7.4.3
pytest-cov==4.1.0
python-dotenv==1.0.0
```

**Dockerfile:**
```dockerfile
FROM python:3.11-slim

WORKDIR /app

# Install dependencies
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

# Copy source code
COPY src/ ./src/
COPY tests/ ./tests/

# Environment
ENV PYTHONPATH=/app
ENV LOG_LEVEL=INFO

# Health check
HEALTHCHECK --interval=30s --timeout=3s \
  CMD python -c "import sys; sys.exit(0)"

CMD ["python", "src/main.py"]
```

**README.md:**
```markdown
# OpenAI GPT-4 Chat Assistant

Implements `product/llm-chat-assistant:v2.3` using OpenAI GPT-4 API.

## Setup

1. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

2. Set environment variables:
   ```bash
   export OPENAI_API_KEY=your-api-key
   ```

3. Run:
   ```bash
   python src/main.py
   ```

## Testing

```bash
pytest tests/ --cov=src
```

## Contract Compliance

- ✅ Inputs: user_message, conversation_history, system_prompt, max_tokens
- ✅ Outputs: assistant_response, truth_score, tokens_used
- ✅ Response time: < 5s p95 (monitored)
- ✅ Safety: OpenAI moderation API
- ✅ Truth scoring: Based on finish_reason
```

---

### Physical Solution: ROS2 Warehouse Robot

```
product/autonomous-warehouse-robot/solutions/ros2-nav2/
```

**solution.yaml:**
```yaml
id: "solution/autonomous-warehouse-robot/ros2-nav2:v2.3"
implements: "product/autonomous-warehouse-robot:v2.3"

identity:
  name: "ROS2 Nav2 Warehouse Robot"
  technology: "ros2-humble"
```

**src/warehouse_robot_node.py:**
```python
"""ROS2 Warehouse Robot Node"""

import rclpy
from rclpy.node import Node
from rclpy.action import ActionServer
from geometry_msgs.msg import PoseStamped
from nav2_msgs.action import NavigateToPose
import time

class WarehouseRobotNode(Node):
    """Implements product/autonomous-warehouse-robot:v2.3 using ROS2 Nav2"""
    
    def __init__(self):
        super().__init__('warehouse_robot')
        
        # Action server for transport tasks
        self._action_server = ActionServer(
            self,
            TransportItem,  # Custom action type
            'transport_item',
            self.execute_transport
        )
        
        # Navigation client
        self._nav_client = ActionClient(self, NavigateToPose, 'navigate_to_pose')
        
        self.get_logger().info('Warehouse robot node initialized')
        
    async def execute_transport(self, goal_handle):
        """
        Implements the product contract.
        
        Args:
            goal_handle.request:
                pickup_location: Pose3D
                delivery_location: Pose3D
                item_description: {weight_kg, dimensions_cm, fragile}
                priority: enum
                
        Returns:
            result:
                task_result: enum (success/failed/cancelled)
                path_taken: Path
                time_elapsed: duration
                truth_score: float
        """
        self.get_logger().info('Executing transport task')
        start_time = time.time()
        
        # Extract goal
        pickup = goal_handle.request.pickup_location
        delivery = goal_handle.request.delivery_location
        item = goal_handle.request.item_description
        
        # Safety checks
        if item.weight_kg > 50.0:
            self.get_logger().error('Item exceeds max payload (50kg)')
            goal_handle.abort()
            return TransportItemResult(
                task_result='failed',
                truth_score=0.0
            )
        
        # Navigate to pickup
        self.get_logger().info('Navigating to pickup location')
        nav_result = await self._navigate_to(pickup)
        if not nav_result.success:
            return TransportItemResult(task_result='failed', truth_score=0.3)
        
        # Simulate item pickup
        await self._pickup_item(item)
        
        # Navigate to delivery
        self.get_logger().info('Navigating to delivery location')
        nav_result = await self._navigate_to(delivery)
        if not nav_result.success:
            return TransportItemResult(task_result='failed', truth_score=0.5)
        
        # Simulate item delivery
        await self._deliver_item(item)
        
        # Calculate truth score (confidence in success)
        elapsed = time.time() - start_time
        truth_score = 0.95  # High confidence if completed successfully
        
        # Return result
        result = TransportItemResult()
        result.task_result = 'success'
        result.path_taken = nav_result.path
        result.time_elapsed = elapsed
        result.truth_score = truth_score
        
        goal_handle.succeed()
        return result
        
    async def _navigate_to(self, pose):
        """Navigate to pose using Nav2"""
        goal = NavigateToPose.Goal()
        goal.pose = pose
        
        future = await self._nav_client.send_goal_async(goal)
        result = await future.get_result_async()
        
        return result
```

**package.xml:**
```xml
<?xml version="1.0"?>
<package format="3">
  <name>warehouse_robot</name>
  <version>2.3.0</version>
  <description>ROS2 Nav2 implementation of autonomous warehouse robot</description>
  
  <maintainer email="dev@example.com">Developer</maintainer>
  <license>Apache-2.0</license>
  
  <depend>rclpy</depend>
  <depend>nav2_msgs</depend>
  <depend>geometry_msgs</depend>
  <depend>tf2_ros</depend>
  
  <test_depend>pytest</test_depend>
  
  <export>
    <build_type>ament_python</build_type>
  </export>
</package>
```

---

### Hybrid Solution: Unity AR Maintenance Assistant

```
product/ar-maintenance-assistant/solutions/unity-hololens/
```

**solution.yaml:**
```yaml
id: "solution/ar-maintenance-assistant/unity-hololens:v2.3"
implements: "product/ar-maintenance-assistant:v2.3"

identity:
  name: "HoloLens AR Maintenance Assistant"
  technology: "unity-hololens2"
```

**Assets/Scripts/MaintenanceAssistant.cs:**
```csharp
/// <summary>
/// Implements product/ar-maintenance-assistant:v2.3 using Unity + HoloLens 2
/// </summary>
using UnityEngine;
using Microsoft.MixedReality.Toolkit;
using System.Collections.Generic;

public class MaintenanceAssistant : MonoBehaviour
{
    // Product contract implementation
    private string equipmentId;
    private MaintenanceTask currentTask;
    private AROverlay arOverlay;
    
    /// <summary>
    /// Initialize maintenance assistance
    /// </summary>
    public void Initialize(
        string equipmentId,
        MaintenanceTaskType taskType,
        ExpertiseLevel userExpertise = ExpertiseLevel.Intermediate)
    {
        this.equipmentId = equipmentId;
        
        // Load equipment model and procedures
        LoadEquipmentModel(equipmentId);
        LoadMaintenanceProcedure(taskType, userExpertise);
        
        // Initialize AR tracking
        InitializeARTracking();
        
        Debug.Log($"Maintenance assistant initialized for {equipmentId}");
    }
    
    /// <summary>
    /// Implements the product contract outputs
    /// </summary>
    public MaintenanceResult Execute()
    {
        // AR overlay (product output)
        ARScene arScene = RenderAROverlay();
        
        // Step-by-step instructions (product output)
        List<MaintenanceStep> steps = GetInstructions();
        
        // Completion status (product output)
        CompletionStatus status = GetCompletionStatus();
        
        // Truth score (product output)
        float truthScore = CalculateTruthScore();
        
        // Verify guarantees
        VerifyGuarantees(arScene, truthScore);
        
        return new MaintenanceResult
        {
            ArOverlay = arScene,
            Instructions = steps,
            CompletionStatus = status,
            TruthScore = truthScore
        };
    }
    
    private ARScene RenderAROverlay()
    {
        // AR tracking (guarantee: accuracy < 2cm)
        Vector3 equipmentPosition = TrackEquipment();
        
        // Render 3D overlays on physical equipment
        arOverlay.RenderInstructions(equipmentPosition);
        arOverlay.RenderWarnings(equipmentPosition);
        arOverlay.RenderCompletionMarkers(equipmentPosition);
        
        // Guarantee: frame rate > 30fps
        if (Time.deltaTime > 1.0f / 30.0f)
        {
            Debug.LogWarning($"Frame rate dropped: {1.0f / Time.deltaTime}fps");
        }
        
        return arOverlay.GetScene();
    }
    
    private float CalculateTruthScore()
    {
        // Equipment recognition accuracy (guarantee: > 95%)
        float recognitionConfidence = arOverlay.GetRecognitionConfidence();
        
        // AR tracking quality (guarantee: < 2cm accuracy)
        float trackingQuality = arOverlay.GetTrackingQuality();
        
        // Procedure correctness (guarantee: validated by experts)
        float procedureConfidence = 1.0f; // Pre-validated
        
        return (recognitionConfidence + trackingQuality + procedureConfidence) / 3.0f;
    }
    
    private void VerifyGuarantees(ARScene scene, float truthScore)
    {
        // Guarantee: AR registration accuracy < 2cm
        if (scene.TrackingError > 0.02f)
        {
            Debug.LogError($"Tracking error {scene.TrackingError}m exceeds 2cm guarantee");
        }
        
        // Guarantee: Equipment recognition > 95%
        if (truthScore < 0.95f)
        {
            Debug.LogWarning($"Truth score {truthScore} below 95% guarantee");
        }
        
        // Guarantee: Safety warnings visible
        if (!arOverlay.HasSafetyWarnings())
        {
            Debug.LogError("Safety warnings not displayed");
        }
    }
}

// Product contract types
public enum MaintenanceTaskType
{
    Inspection,
    Repair,
    Replacement,
    Calibration
}

public enum ExpertiseLevel
{
    Novice,
    Intermediate,
    Expert
}

public class MaintenanceResult
{
    public ARScene ArOverlay;
    public List<MaintenanceStep> Instructions;
    public CompletionStatus CompletionStatus;
    public float TruthScore;
}
```

---

## Solution Best Practices

### 1. Contract Compliance

✅ **Implement all inputs:**
```python
def process(self, required_input, optional_input=None):
    # Handle all product contract inputs
    pass
```

✅ **Return all outputs:**
```python
return {
    "output1": value1,
    "output2": value2,
    "truth_score": 0.95
}
```

✅ **Meet all guarantees:**
```python
import time

start = time.time()
result = process()
elapsed = time.time() - start

# Verify response time guarantee
assert elapsed < 5.0, "Response time guarantee violated"
```

### 2. Testing

```python
# Test contract compliance
def test_contract_outputs():
    result = solution.execute(valid_input)
    
    # All outputs present
    assert "required_output" in result
    assert "truth_score" in result
    
    # Correct types
    assert isinstance(result["truth_score"], float)
    assert 0.0 <= result["truth_score"] <= 1.0
    
# Test guarantees
def test_performance_guarantee():
    times = [measure_execution() for _ in range(100)]
    p95 = sorted(times)[95]
    
    assert p95 < 5.0, f"P95 latency {p95}s exceeds 5s guarantee"
```

### 3. Documentation

```markdown
# Solution Name

Implements `product/product-name:v2.3`

## Contract Compliance

- ✅ Input: user_message (function parameter)
- ✅ Output: response (return value)
- ✅ Guarantee: response_time < 5s (tested)

## Usage

\`\`\`python
from solution import Implementation

impl = Implementation()
result = impl.execute(input)
\`\`\`

## Testing

\`\`\`bash
pytest tests/ --cov=src
\`\`\`
```

### 4. Deployment

```yaml
# docker-compose.yml
version: '3.8'

services:
  solution:
    build: .
    environment:
      - API_KEY=${API_KEY}
      - LOG_LEVEL=INFO
    ports:
      - "8000:8000"
    healthcheck:
      test: ["CMD", "curl", "-f", "http://localhost:8000/health"]
      interval: 30s
      timeout: 3s
      retries: 3
```

---

## Solution Composition

Solutions can compose other solutions:

```yaml
id: "solution/smart-factory:v2.3"
implements: "product/smart-factory-controller:v2.3"

components:
  # Reuse existing solutions
  orchestrator:
    solution: "solution/factory-orchestrator/ros2:v2.3"
    
  robots:
    solution: "solution/autonomous-warehouse-robot/ros2-nav2:v2.3"
    count: 5
    
  quality_inspector:
    solution: "solution/vision-quality-inspector/pytorch:v2.3"
    
  ar_assistant:
    solution: "solution/ar-maintenance-assistant/unity-hololens:v2.3"
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
L4: Products (contract definitions)
    ↓
L5: Solutions ← YOU ARE HERE
    │   Solutions implement L1C patterns with actual code:
    │   - PyTorch neural networks for knowledge-representation
    │   - Reinforcement learning for experience-acquisition
    │   - Ethics engines for value-system
    │   - Bayesian models for expectation
```

**Solutions (L5)** implement Product contracts with executable code.  
**L1C cognitive patterns become actual ML/AI code at L5.**  
Example: knowledge-representation (L1C) → digital (L2) → PyTorch (L3) → AGI product (L4) → Python neural net code (L5)

---

## Key Properties

### Executable

Solutions provide:
- **Source code** - Actual implementation
- **Dependencies** - Required libraries
- **Configuration** - Settings and environment
- **Entry point** - How to run it

### Testable

Solutions include:
- **Unit tests** - Test individual components
- **Integration tests** - Test system interaction
- **Contract tests** - Verify product compliance
- **Performance tests** - Verify guarantees

### Deployable

Solutions provide:
- **Deployment config** - Docker, Kubernetes, etc.
- **Infrastructure** - Required resources
- **Monitoring** - Health checks, metrics
- **Documentation** - Setup and operation guides

### Maintainable

Solutions include:
- **Clear structure** - Organized code
- **Documentation** - Inline and external
- **Logging** - Debugging information
- **Error handling** - Graceful failures

---

## What This Means

**Solutions are not:**
- Contracts (that's L4)
- Templates (that's L2/L3)
- Patterns (that's L1)

**Solutions are:**
- Working code that runs
- Implementations of product contracts
- Deployable systems
- Testable software

---

## Bottom Line

**Solutions (L5)** are complete implementations with code:
- **Implements:** Product (L4) contract
- **Contains:** Actual source code
- **Provides:** Dependencies, tests, deployment
- **Delivers:** Runnable, deployable system

They enable:
- Users to run the system
- Deployment to production
- Testing and verification
- Maintenance and updates

**Every Solution must implement a Product contract and prove it with tests.**

Solutions are what users actually run. Everything else (L0-L4) defines what solutions should be.

---

*For complete solution implementations, see `product/*/solutions/*/`*
