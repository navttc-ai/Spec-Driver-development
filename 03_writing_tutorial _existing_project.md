This is a formalized, **File-Based CI/CD Pipeline for Technical Education**. By treating documentation as code artifacts (`research.md`, `architecture.md`, `spec.md`), you ensure a deterministic output where any AI or collaborator can maintain the same level of context and quality.

---

### 📂 The Artifact Chain
Every phase produces a "Source of Truth" file used by the next phase:
1.  **`research.md`**: The raw technical audit of the codebase.
2.  **`filteredResearch.md`**: The customized roadmap (pruned based on your knowledge).
3.  **`architecture.md`**: The structural "Table of Contents" (Modules/Lessons).
4.  **`spec.md`**: The formatting, tone, and technical constraints.
5.  **`Content (.md)`**: The final educational chapters.

---

### 🚀 The Execution Pipeline (Prompts)

#### Phase 1: Deep Research
*Use this to map out the entire repository and identify core concepts.*
```text
[RESEARCH PHASE]
Audit the entire project directory. Analyze all architecture, logic, libraries, and patterns. Generate a comprehensive research document at `docs/textbook/research.md`. List every core engineering concept required for a beginner to master this project.
```

#### Phase 2: Filtering
*Use this to remove topics you already understand.*
```text
[FILTER PHASE]
Read `docs/textbook/research.md`. I already possess knowledge of: [INSERT TOPICS HERE]. Please generate `docs/textbook/filteredResearch.md` by removing those specific topics, while keeping all other research findings and technical requirements identical.
```

#### Phase 3: Architecture Design
*Use this to build the structural skeleton of the textbook.*
```text
[ARCHITECTURE PHASE]
Read `docs/textbook/filteredResearch.md`. Design the full tree structure for the textbook. Output the architecture to `docs/textbook/architecture.md`, defining Modules and specific Lesson file paths (e.g., `docs/textbook/module_1/lesson_1_1.md`).
```

#### Phase 4: Specification Drafting
*Use this to set the "Rules of Engagement" for the writing style.*
```text
[SPECIFICATION PHASE]
Read `docs/textbook/architecture.md`. Draft a `docs/textbook/spec.md`. This file must define: 
1. The mandatory 6-section markdown template for every lesson. 
2. Rules for grounding content in actual repository code snippets. 
3. Tone and educational fluency requirements (e.g., "explain like I'm an intermediate dev"). 
4. Code hygiene and syntax highlighting standards.
```

#### Phase 5: Clarification (The Interview)
*Use this to let the AI find gaps in your requirements before it starts writing.*
```text
[CLARIFICATION PHASE]
Review `docs/textbook/spec.md`. As a technical editor, interview me to identify any gaps in these specifications. Ask me specific questions about: 
1. Preferred depth of technical explanations. 
2. How to handle cross-references between chapters. 
3. Whether code snippets should be modular snippets or full-file context. 

Update `docs/textbook/spec.md` with my answers to solidify the final writing requirements.
```

#### Phase 6: Content Generation
*The final step: Generate specific lessons one by one.*
```text
[CONTENT PHASE]
Read `docs/textbook/architecture.md` and the final `docs/textbook/spec.md`. Generate the chapter for: [INSERT FILE PATH, e.g., docs/textbook/module_1/lesson_1_1.md]. Ensure it strictly follows the templates and rules defined in `spec.md`.
```

---

### 📋 Setup & Getting Started

Before running the prompts, prepare your local environment by creating the necessary directory:

```bash
mkdir -p docs/textbook
```

**Next Step:**
To begin, paste the **Phase 1: Deep Research** prompt into your AI chat. Once the `research.md` file is generated, proceed to Phase 2.
