# Contributing to SPL

🎉 **Thank you for your interest in contributing to SPL!**

We're building the future of verifiable AI, and we need your help. Whether you're a developer, domain expert, researcher, or enthusiast, there's a place for you here.

## 🌟 Ways to Contribute

### 1. **Create Patterns**

The most valuable contribution is creating new patterns!

**What we need:**
- **L1 Critical Patterns**: New fundamental building blocks
- **L2 Cognitive Patterns**: Implement the cognitive framework (value-system, knowledge-representation, etc.)
- **L3 Reality Patterns**: Domain-specific patterns (legal, medical, finance, science)
- **L4 Technology Patterns**: Framework-specific patterns (React, Django, TensorFlow, etc.)
- **L5 Products**: Reusable product components
- **L6 Solutions**: Complete end-to-end solutions

**How to create a pattern:**
1. Follow the meta-pattern structure in `patterns/meta-pattern/v2.3/meta-pattern.yaml`
2. Place it in the correct layer directory
3. Add comprehensive documentation
4. Include examples and test cases
5. Submit a pull request

### 2. **Improve Documentation**

- Fix typos and clarify explanations
- Add tutorials and guides
- Create example use cases
- Translate documentation
- Write blog posts about SPL

### 3. **Build Tools**

We need tooling to make SPL easier to use:

- Pattern validators
- Composition analyzers
- Truth score calculators
- IDE extensions (VS Code, IntelliJ)
- CLI tools
- Web-based pattern explorers

### 4. **Report Issues**

Found a bug or have a suggestion?

- Check if it's already reported
- Provide clear reproduction steps
- Include pattern YAML examples
- Suggest solutions if possible

### 5. **Answer Questions**

Help others in:
- GitHub Discussions
- Issue comments
- Stack Overflow (tag: `spl`)

## 📋 Contribution Guidelines

### Pattern Contributions

**Requirements:**
- Must follow meta-pattern v2.3 structure
- Must include clear `goal`, `return_format`, `warnings`, and `context`
- Must specify correct `layer` (L0-L6)
- Must declare all `dependencies`
- Must include documentation in the pattern YAML
- Must include version number (semantic versioning)

**Quality Standards:**
- Patterns should be self-documenting
- Examples should be concrete and runnable
- Dependencies should be minimal and justified
- Truth scoring mechanisms should be explicit

**Pattern Structure:**
```yaml
pattern_id: "your-pattern:v1.0"
layer: "L1"  # or L2, L3, L4, L5, L6
pattern_type: "validator"  # One of 13 L1 types

metadata:
  name: "Your Pattern Name"
  version: "2.3"
  description: "Clear description"
  author: "Your Name"
  license: "Apache-2.0"
  
goal:
  description: "What this pattern achieves"
  success_criteria:
    - "Measurable criteria 1"
    - "Measurable criteria 2"

return_format:
  type: "structured"
  structure:
    # Define your output format
    
warnings:
  - "Important limitation 1"
  - "Important limitation 2"
  
context:
  input_reality: "source-domain"
  output_reality: "target-domain"
  
dependencies:
  - id: "dependency-pattern:v1.0"
    layer: "L1"
```

### Code Style

- **YAML**: Use 2-space indentation
- **Documentation**: Use Markdown
- **Examples**: Include inline comments
- **Naming**: Use `kebab-case` for pattern IDs

### Commit Messages

Use conventional commits:
```
feat: Add legal contract validator pattern
fix: Correct truth score calculation in validator
docs: Improve cognitive patterns documentation
test: Add test cases for orchestrator pattern
```

### Pull Request Process

1. **Fork the repository**
2. **Create a feature branch**: `git checkout -b feature/your-pattern-name`
3. **Make your changes**
4. **Test thoroughly** (include examples)
5. **Update documentation**
6. **Commit with clear messages**
7. **Push to your fork**
8. **Open a Pull Request**

**PR Description Should Include:**
- What pattern/feature you're adding
- Why it's needed
- How it works
- Examples of usage
- Any breaking changes
- Related issues (if any)

### Review Process

All contributions are reviewed for:
- ✅ Correctness: Does it follow the meta-pattern?
- ✅ Quality: Is it well-documented and tested?
- ✅ Utility: Does it solve a real problem?
- ✅ Compatibility: Does it work with existing patterns?

Expect feedback within 1-3 days. We may request changes before merging.

## 🎯 Priority Areas

### High Priority

1. **Cognitive Pattern Implementations** (L2)
   - value-system
   - knowledge-representation
   - experience-acquisition
   - motivation
   - expectation
   - ethical-reasoning

2. **Domain-Specific Reality Patterns** (L3)
   - Legal domain patterns
   - Medical domain patterns
   - Financial domain patterns
   - Scientific domain patterns

3. **Validation Tools**
   - Pattern structure validator
   - Dependency checker
   - Truth score calculator
   - Quality analyzer

### Medium Priority

4. **Technology Patterns** (L4)
   - Popular framework patterns
   - Language-specific patterns
   - Cloud platform patterns

5. **Documentation**
   - Tutorial series
   - Video guides
   - Pattern cookbook
   - Best practices guide

### Lower Priority

6. **Ecosystem Tools**
   - IDE extensions
   - Web-based explorers
   - Pattern generators

## 🤝 Community Guidelines

### Be Respectful
- Assume good intentions
- Provide constructive feedback
- Welcome newcomers
- Celebrate contributions

### Be Clear
- Write clear documentation
- Explain your reasoning
- Ask questions when confused
- Provide examples

### Be Collaborative
- Review others' PRs
- Share knowledge
- Help troubleshoot issues
- Build on existing work

## 📚 Resources

- **[Meta-Pattern v2.3](doc/meta-pattern-v2.3-changes.md)**: Pattern structure specification
- **[Layer Enforcement](doc/layer-enforcement-v2.3.md)**: Architecture rules
- **[Versioning Policy](doc/SPL_VERSIONING_POLICY.md)**: How to version patterns
- **[Cognitive Patterns](doc/spl-cognitive-patterns-a-comprehensive-framework.md)**: L2 framework

## 🆘 Getting Help

- **Questions**: Open a discussion in this repository
- **Bugs**: Open an issue in this repository
- **Security**: Use the repository's security policy once available

## 📜 Legal

By contributing, you agree that your contributions will be licensed under the Apache License 2.0.

---

## 🚀 Let's Build the Future

SPL is ambitious: we're building verifiable AI for **every domain**. This requires:
- Hundreds of patterns across all layers
- Validation tools and quality metrics
- Documentation and tutorials
- Community support and collaboration

**Your contribution matters.** Whether it's a single pattern, a documentation fix, or a major feature, you're helping build the foundation for verifiable AI.

**Let's change the world together.**

— The SPL Team

---

**First contribution?** Look for issues labeled “good first issue” in this repository to get started!
