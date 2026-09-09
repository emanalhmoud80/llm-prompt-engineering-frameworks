# Case Study: Multi-Constraint Academic Advice Prompt Engineering

## Overview
This case study demonstrates the design and execution of a highly structured system prompt designed for educational AI assistance. The objective was to force the Large Language Model (LLM) to deliver targeted math review techniques (Calculus & Trigonometric Identities) alongside general study habits while adhering to strict structural, word count, and logical boundary constraints.

---

## 1. The Raw System Prompt
> "I have a math exam tomorrow at school and I need some tips before the exam. Specifically, I need tips for reviewing calculus. I also want methods to verify my answers in trigonometric identities.
>
> Write me a response of at most 500 words. Divide the answer into 'Study Tips' and 'General Tips'. Include calculus review tips and answer verification methods under 'Study Tips', and tips for sleep, food, etc. under 'General Tips'. Include at least 3 points under each section. End the response with a motivational word."

---

## 2. Engineering & Constraint Breakdown

| Constraint Type | Explicit Rule | Implementation Strategy |
| :--- | :--- | :--- |
| **Output Length** | At most 500 words | Enforced conciseness by capping bullet points and removing filler intro/outro text. |
| **Structural Division** | Exactly two main sections: `نصائح دراسية` (Study Tips) and `نصائح عامة` (General Tips) | Applied strict Markdown headers (`**نصائح دراسية**` and `**نصائح عامة**`) to enforce visual separation. |
| **Section Content (A)** | Calculus review + Trig identity verification under *Study Tips* | Grouped mathematical strategies into explicit sub-bullets under Section 1. |
| **Section Content (B)** | Sleep, nutrition, and exam mindset under *General Tips* | Reserved wellness advice strictly for Section 2 to avoid cross-domain drift. |
| **Minimum Count** | At least 3 points per section | Indexed key strategies into 3 distinct, actionable bullet groups per main section. |
| **Ending Constraint** | Conclude with a single motivational word | Appended `**بالتوفيق!**` (Good luck!) as the final line. |

---

## 3. Key Challenge & Edge-Case Handling

### **Challenge: Preventing Knowledge Drift Across Categories**
* **Issue:** Models frequently mix lifestyle advice (e.g., "take breaks while studying") into study tips or put mathematical verification steps under general test-taking strategies.
* **Resolution:** Explicit category mapping was enforced in the system directive. The prompt bound "trigonometric verification methods" directly to the "Study Tips" node, ensuring the model did not generate floating or miscategorized advice.

### **Challenge: Exact Word Limit Adherence (<500 words)**
* **Issue:** Detailed mathematical steps (e.g., showing trigonometric substitutions like $\sin^2\theta + \cos^2\theta = 1$) can cause verbosity explosions.
* **Resolution:** Used concise, imperative phrasing and inline LaTeX notation ($e^x$, $\theta$, $30^\circ$) to keep explanations short and clear.

---

## 4. Model Output Evaluation

* **Structural Integrity:** Passed (2 distinct sections created).
* **Point Count:** Passed (3 detailed sub-points under Study Tips; 3 under General Tips).
* **Topic Categorization:** Passed (Calculus & Trigonometric verification strictly placed in Study Tips; Sleep & Food strictly in General Tips).
* **Word Count:** Passed (~280 words, well within the 500-word limit).
* **Ending Anchor:** Passed (Ended with the exact required closing).

---

## 5. Key Takeaway for Prompt Architecture
When engineering system prompts for LLMs under negative or multi-layered constraints:
1. **Explicitly map requirements to output sections** (e.g., "Put X and Y under Section 1").
2. **Combine stylistic constraints with content limits** (e.g., word count caps paired with minimum list item counts force high information density).
