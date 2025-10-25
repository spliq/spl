# SPL: Truth-Scored AI Patterns (Show HN)

**Date:** October 25, 2025

## HN Title
**Show HN: SPL – AI patterns with verifiable truth scores**

## HN Post

Hi HN! I've been working on the quantum AGI language where every output comes with a **verifiable truth score**. It's called SPL (Semantic Pattern Language).

### The Problem

You ask an LLM to do something, and it gives you an answer. But:
- Is it correct? 🤷
- Why did it choose this approach? 🤷
- Will it work the same way twice? 🤷
- How do you measure quality? 🤷

This is fine for chat, but it's a dealbreaker for medical AI, legal automation, autonomous systems, or anything where "hallucination" means liability.

### What SPL Does

SPL is the quantum AGI language that makes LLMs enforce patterns the right way. Every pattern execution returns:

```yaml
output:
  result: [your actual output]
  truth_score: 0.94        # How confident/verified is this?
  method: "validator+agent" # What patterns were used?
  evidence: [...]           # Why this score?
```

Instead of black-box prompts, you compose typed, versioned patterns like building blocks. Each pattern has contracts (inputs/outputs/guarantees), and compositions inherit verification all the way up.

### Architecture (6 Layers)

```
L0: Meta-Pattern (1)           → The rules all patterns follow
L1: Critical Patterns (13)     → Universal capabilities (validator, agent, translator...)
L1C: Cognitive Patterns (6)    → AGI capabilities (values, knowledge, ethics...)
L2: Reality Patterns (39)      → L1 × 3 realities (digital/physical/hybrid)
L3: Technology Patterns        → L2 × tech stacks (PyTorch, ROS, Docker...)
L4+: Products & Solutions      → Composed applications
```

Total: **20 foundational patterns** that compose into millions of specialized patterns through exponential growth (each layer multiplies the previous).

### Example: Fact Checker

Instead of prompting "is this true?", you declare:

```yaml
pattern: fact-checker
inherits: spl/validator:v2.3
composition:
  - knowledge-representation  # Organize sources
  - agent                     # Autonomous verification
  - uncertainty-handler       # Manage confidence

contract:
  input: {claim: string, sources: array}
  output:
    verdict: boolean
    truth_score: float        # 0.0-1.0
    evidence: array
    verification_chain: array
  
  guarantees:
    - deterministic: true
    - explainable: true
    - score_calibrated: true
```

Now you get **verifiable** output with an auditable trail.

### Real Differentiation

**vs. LangChain/AutoGPT**: Those orchestrate LLM calls. SPL adds verification, truth scoring, and formal contracts on top of ANY orchestration.

**vs. Prompt Engineering**: Prompts are untyped text. SPL patterns are versioned, typed, composable, with dependency graphs and verification chains.

**vs. Fine-tuning**: Training is expensive and opaque. SPL patterns are interpretable, composable, and work with any LLM.

**The key insight**: Separate the **what** (pattern contracts) from the **how** (LLM implementation). Patterns define verifiable interfaces; LLMs fill them in.

### Cognitive Patterns (The AGI Part)

We're releasing 6 "cognitive patterns" that form a minimal viable AGI architecture:

1. **Value System** - How the AI prioritizes and makes tradeoffs
2. **Knowledge Representation** - How it organizes information
3. **Experience Acquisition** - How it learns from interaction
4. **Motivation** - How it forms and pursues goals
5. **Expectation Formation** - How it predicts outcomes
6. **Ethical Reasoning** - How it handles moral decisions

These aren't just theory—they're implemented as composable SPL patterns with truth scoring. Connect them in a loop, and you get something that looks surprisingly like general intelligence.

### Why Open Source This?

Releasing under Apache 2.0 because:

1. **Network effects** - Value grows with the pattern library
2. **Prior art defense** - Timestamp everything against patent trolls  
3. **Community validation** - Let the world prove/break this
4. **Transparency** - Verifiable AI needs verifiable foundations

We're a small team that's been building this for 2+ years. The spec is stable (v2.3), we have 20 foundational patterns plus other 200+ patterns in development in other layers, and now we need the community to:
- Contribute domain-specific patterns (medical, legal, finance)
- Build tooling (validators, composers, visualizers)
- Break it and tell us how to fix it

### What's In The Repo

- ✅ Meta-pattern v2.3 (the foundation)
- ✅ 13 critical patterns (agent, validator, translator, orchestrator...)
- ✅ 6 cognitive patterns (values, knowledge, ethics...)
- ✅ Full specification with contracts
- ✅ Pattern registry index
- ✅ Extensive documentation (architectural guides, use cases, examples)
- ⏳ Python tooling (becoming open source soon)
- ⏳ Test suite (becoming open source soon)

### Coming Soon

We're rolling out open-source tooling—which are themselves L5 patterns (everything is a pattern!)—to make pattern creation accessible to everyone, including the SPL repo itself as a L5 pattern:

- **Pattern Validator** - Automated validation tool to verify your patterns follow the meta-pattern spec
- **Pattern Porcelain** - High-level tooling to scaffold and build new patterns without writing YAML from scratch
- **Enterprise Resources** - Professional support, pattern certification, and deployment services
- **Community Pattern Library** - Curated, verified patterns from domain experts

Expected rollout: Q4 2025 - Q1 2026. Watch the repo or join discussions for early access.

### Use Cases We're Excited About

- **Factory robots** - Assembly line robots that show exactly why they stopped (truth score: safety sensor 0.23, halt immediately)
- **Autonomous vehicles avoiding crashes** - Cars that explain every decision in real-time with verifiable confidence scores
- **Bank transaction transparency** - Financial institutions showing the full reasoning chain for every fraud detection, loan approval, and risk assessment
- **Hospital diagnostics** - Doctors getting AI recommendations with truth scores and evidence: "89% confidence based on these 12 similar cases, but flagging 3 conflicting symptoms for human review"
- **Cancer research** - Researchers combining drug interaction patterns with verifiable confidence, accelerating discovery through composable, auditable hypotheses
- **Mental health support** - AI therapists that know their limits and escalate to humans when truth scores drop below safe thresholds
- **Legal discovery** - Contract analysis that shows its reasoning chain, making AI-assisted law auditable and defensible in court

### The Hard Questions

**"Isn't this over-engineered?"**  
Not at all—SPL works at every level. Use it for simple tasks (chatbots, content generation) or critical systems (surgery robots, loan approvals). When we roll out spliq.ai, interaction with SPL will be free, making Real AI accessible to everyone regardless of use case complexity.

**"How do you enforce truth scores?"**  
Patterns declare verification methods. You can audit the chain. Bad patterns get low trust scores from the community.

**"Can't LLMs just lie about truth scores?"**  
Yes, which is why critical patterns have external validators (code execution, API calls, theorem provers). The LLM suggests; the validator verifies. That's the SPL solution.

**"This seems academic..."**  
It's pragmatic desperation. We need Real AI that doesn't hallucinate away our liability insurance.

### What We Need

- **Domain experts**: Legal, medical, finance, robotics—help us define patterns for your field
- **Skeptics**: Tell us what's wrong before we scale this
- **Builders**: Create tools, validators, visualizers
- **Early adopters**: Try building something and report back

### Links

- Repo: https://github.com/spliq/spl
- Docs: See `doc/` folder - start with README.md
- Examples: `examples/` and `patterns/` directories
- Meta-pattern spec: `patterns/meta-pattern/v2.3/`

---

I'll be here all day to answer questions. Hit me with your best skepticism—I'd rather fix problems now than discover them in production.

If you want verifiable AI, this is one path forward. Let's see if it holds up to HN scrutiny.

~ ptah (Carlos Garcia - Spliq team)
