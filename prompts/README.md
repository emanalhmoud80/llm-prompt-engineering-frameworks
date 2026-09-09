# Production System Prompt Templates

This directory contains production-ready system prompts engineered for complex LLM tasks, constraint adherence, and structured evaluations.

## Included Templates
* [`complex-constraint-prompt.md`](./complex-constraint-prompt.md): System prompt enforcing strict word counts, negative keyword filtering, and structural output formats.
* [`evaluator-rubric-prompt.md`](./evaluator-rubric-prompt.md): Prompt designed to evaluate model responses against step-by-step logic and accuracy rubrics.

## Design Methodology
All prompts in this collection utilize:
1. **Explicit Role Assignment:** Framing the model's persona and core task boundaries.
2. **Negative Constraint Blocks:** Explicit rules declaring prohibited vocabulary and formatting errors.
3. **Structured Outputs:** Dictating exact JSON, XML, or Markdown schema outputs.
