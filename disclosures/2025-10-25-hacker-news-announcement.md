# SPL: Truth-Scored AI Patterns (Show HN)

**Date:** October 25, 2025

## HN Title
**Show HN: SPL – AI patterns with verifiable truth scores**

## HN URL
https://news.ycombinator.com/item?id=45703516

## HN Post

Hi HN! I've been working on a quantum AGI language where every output comes with a verifiable truth score. It's called SPL (Semantic Pattern Language).

GitHub: https://github.com/spliq/spl  
Youtube: https://youtube.com/shorts/9mrsAQFfCTI

The Problem

Current AI hallucinates. Fine for chat, dealbreaker for medical AI, legal automation, autonomous systems—anything where errors mean liability.

What SPL Does

Every pattern execution returns:

output:
  result: [your output]
  truth_score: 0.94        # Verifiable confidence
  method: "validator+agent"
  evidence: [...]

Instead of black-box prompts, you compose typed, versioned patterns with contracts. Each pattern has guarantees that compose all the way up.

Architecture

20 foundational patterns across 6 layers that compose into millions through exponential growth:
- L0: Meta-Pattern (rules all patterns follow)
- L1: 13 Critical Patterns (validator, agent, translator...)
- L1C: 6 Cognitive Patterns (values, knowledge, ethics...)
- L2+: Reality × Technology × Products

Key Differentiation

vs. LangChain/AutoGPT: They orchestrate. SPL adds verification + truth scoring + formal contracts.

vs. Prompt Engineering: Prompts = untyped text. SPL = versioned, typed, composable, with dependency graphs.

The insight: Separate what (pattern contracts) from how (LLM implementation). The LLM proposes; validators verify.

Cognitive Patterns (AGI Part)

6 patterns forming minimal viable AGI:
1. Value System - priorities/tradeoffs
2. Knowledge Representation - organizing info
3. Experience Acquisition - learning
4. Motivation - goal formation
5. Expectation - predictions
6. Ethical Reasoning - moral decisions

Connect them in a loop → general intelligence.

Why Open Source?

Apache 2.0 because:
- Network effects (value grows with pattern library)
- Prior art defense (timestamp against patents)
- Community validation (prove/break this)
- Transparency (verifiable AI needs verifiable foundations)

2+ years building. Spec stable (v2.3). 20 foundational + 200+ patterns in development.

What's In The Repo

✅ Meta-pattern v2.3  
✅ 13 critical + 6 cognitive patterns  
✅ Full specs with contracts  
✅ Extensive docs  
⏳ Python tooling (Q4 2025)  
⏳ Test suite (Q1 2026)

Use Cases

- Factory robots explaining why they stopped
- Autonomous vehicles with verifiable decisions
- Hospital diagnostics with evidence trails
- Legal discovery with auditable reasoning
- AI therapists that escalate when confidence drops

Hard Questions

"Isn't this over-engineered?"  
Works at every level—chatbots to surgery robots. Our platform spliq.ai will make it free.

"How enforce truth scores?"  
Patterns declare verification methods. Audit the chain. Community scores trust.

"Can't LLMs lie?"  
Yes. Critical patterns use external validators (code execution, APIs, theorem provers). LLM suggests; validator verifies.

What We Need

- Domain experts (medical, legal, finance, robotics)
- Skeptics (break it now, not in production)
- Builders (tools, validators, visualizers)
- Early adopters (try it, report back)

---

Here all day for questions. Hit me with skepticism—I'd rather fix problems now.

~ ptah (Carlos Garcia - Spliq team)
