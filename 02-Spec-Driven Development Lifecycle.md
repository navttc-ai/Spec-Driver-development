This refined guide presents the **Specification-Driven Development (SDD)** workflow optimized for **Claude Code**. This methodology shifts the focus from "writing code" to "engineering systems" by using specifications as the source of truth.

---

# 🚀 Specification-Driven Development (SDD) Workflow
**The End-to-End Guide for Claude Code Orchestration**

---

## 🔍 Phase 0: Discovery & Research
**Goal:** Prevent architectural debt by investigating technical requirements before coding begins.

### 📋 Copyable Prompt
```markdown
RESEARCH: Initialize an isolated sub-agent to investigate the technical requirements for [Insert Project/Feature Idea].

Instructions for Sub-agent:
1. Industry Standards: Research how this problem is typically solved in modern engineering.
2. Architecture Options: Provide the top 2-3 technical approaches with pros/cons.
3. System Alignment: Scan the current repo structure and dependencies to ensure compatibility.
4. Critical Failure Modes: Identify edge cases, security risks, or infra bottlenecks.

Output: Save a concise report to `docs/research/research.md`. Return ONLY the finalized report to the main context to prevent token bloat.
```

---

## 📜 Phase 1: Global Governance (The Constitution)
**Goal:** Establish the "Laws of the Repo" in `CLAUDE.md` to automate linting, testing, and styling rules.

### 📋 Copyable Prompt
```markdown
CONSTITUTION: Analyze our tech stack and repository structure. Initialize a sub-agent to draft/update the root `CLAUDE.md` file. 

The file must explicitly document:
1. Build & Test Commands: Precise terminal commands for building, testing, and linting.
2. Code Style: Naming conventions (e.g., PascalCase for components), formatting, and file structure rules.
3. Architecture Patterns: Directory layouts, decoupling rules (Services vs. Controllers), and error-handling paradigms.
4. Testing Mandates: Requirements for coverage, mocking, and naming.

Output: Direct update to `CLAUDE.md`. Return a summary of the established engineering laws.
```

---

## 📐 Phase 2: Macro Blueprint (System Architecture)
**Goal:** Define structural boundaries and fixed technical constraints.

### 📋 Copyable Prompt
```markdown
ARCHITECTURE: Review `docs/research/research.md` and `CLAUDE.md`. Draft a comprehensive `docs/architecture_spec.md`.

Required Sections:
1. Tech Stack: Specific versions of languages, DBs, and frameworks.
2. Data Models: Core schema concepts, relationships, and primitives.
3. Infrastructure Map: Deployment environments, caching layers, and 3rd-party API dependencies.
4. Security Posture: Auth mechanics and data encryption standards.

Rule: No feature implementation details yet; focus strictly on the system boundaries.
```

---

## 🗂️ Phase 3: Modular Decomposition (The Backlog)
**Goal:** Break the global scope into a granular, dependency-aware roadmap.

### 📋 Copyable Prompt
```markdown
EXTRACT: Read `docs/architecture_spec.md`. Break down the project into a list of atomic, modular features.

Output: Generate `FEATURES_BACKLOG.md` organized by logical dependencies (e.g., Infra -> Auth -> Core API). 

For each feature (ID: FEAT-XXX):
- 2-sentence scope description.
- Upstream Dependencies: What must be finished first?
- Functional Goals: A high-level checklist.
```

---

## 📝 Phase 4A: Feature Draft (The Micro-Spec)
**Goal:** Create a behavioral source-of-truth for a single unit of work.

### 📋 Copyable Prompt
```markdown
SPECIFY: We are starting [FEAT-XXX]. Read its entry in `FEATURES_BACKLOG.md`. Spin up a sub-agent to draft `docs/specs/FEAT-XXX.md`.

Must Include:
1. Goal
2. Functional Requirements: API/Data schemas and route definitions.
3. edge cases & rules
4. User Scenarios: Concrete paths through the feature.
5. Boundary Rules: How to handle invalid inputs, timeouts, or empty states.
6. Acceptance Criteria: Quantitative criteria that can be programmatically verified.
7. out-of-scope

Output: Create the spec file. Do not generate any feature code.
```

---

## 🤨 Phase 4B: Spec Hardening (The AI Interview)
**Goal:** Find logical gaps and ambiguities before implementation.

### 📋 Copyable Prompt
```markdown
CLARIFY: Read `docs/specs/FEAT-XXX.md`. Act as an elite, hyper-critical Principal Software Architect. Your goal is to find logical gaps and ambiguities.

The Process:
1. Interview me in the terminal, asking exactly one targeted question at a time.
2. Focus on missing state transitions, validation boundaries, and failure modes.
3. After my response, update `docs/specs/FEAT-XXX.md` to reflect the answer.
4. Continue until you are 100% confident a junior dev could implement this without follow-up.

Exit Criteria: Say "SPEC IS HARDENED" when complete.
```

---

## 🧪 Phase 4C: Executable Truth (TDD Generation)
**Goal:** Lock in requirements by generating failing automated tests.

### 📋 Copyable Prompt
```markdown
TEST_GENERATE: Now that `docs/specs/FEAT-XXX.md` is hardened, initialize a sub-agent to:
1. Read `CLAUDE.md` for testing frameworks and file conventions.
2. Translate every Acceptance Criterion and Edge Case from the spec into automated test blocks.
3. Write these tests to the codebase.
4. Run the tests (using the command in `CLAUDE.md`) and confirm a 100% failure rate.

Output: Terminal logs showing the failing suite. Do not write production logic yet.
```

---

## 🏗️ Phase 5: Sequential Execution (The Build)
**Goal:** Implement code incrementally until all tests pass.

### 📋 Copyable Prompt
```markdown
BUILD: Implement [FEAT-XXX]. Reference the failing tests and `docs/specs/FEAT-XXX.md`.

Instructions:
1. Propose a step-by-step plan to make the tests pass.
2. Once approved, write minimum production code to satisfy one subset of tests at a time.
3. Run the test suite after every change to ensure progress and no regressions.
4. Adhere strictly to the linting/styling in `CLAUDE.md`.

Completion: Once all tests pass, perform a Git commit with conventional commit syntax matching the Feature ID.
```
