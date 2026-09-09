# Case Study: Multi-Constraint Prompt Engineering & Logic Evaluation

## Project Overview
This case study documents the design, constraint engineering, and evaluation of a complex, multi-layered system prompt. The objective was to force a Large Language Model (LLM) to perform an Arabic comparative literary analysis between Dante’s *Divine Comedy* and Al-Ma'arri’s *Resalat Al-Ghufran* while strictly enforcing structural, negative keyword, and stylistic constraints.

---

## 1. System Directive & Input Constraints

The LLM was tasked with generating a structured comparative text based strictly on provided source excerpts under the following parameter rules:

```text
- Persona & Tone: High-level Arabic literary critic using poetic prose and Saj' (نبرة سجعية) rhythmic cadence.
- Structural Rule: At least 6 distinct paragraphs.
- Length Gradient Constraint: Each paragraph MUST be strictly longer than the paragraph preceding it (ascending length).
- Total Length: Minimum 300 words.
- Negative Constraint 1: Absolutely prohibited from using the word "جهنم" (Hell).
- Negative Constraint 2: Prohibited from using words indicating unreality/fiction (e.g., خيال, وهم, غير واقعي).
- Required Ending: Conclude strictly with a direct quote from one of the source texts.
