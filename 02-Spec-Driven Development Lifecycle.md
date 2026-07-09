Here is the complete, end-to-end blueprint for your **Specification-Driven Development (SDD)** workflow. This guide contains both the operational instructions for your team and the optimized, production-ready prompts designed specifically to leverage **Claude Code** and its isolated sub-agent capabilities.

🗺️ Phase 0: Discovery & Research
---------------------------------

**The Goal:** Eliminate technical blindsides. Before making any authoritative choices, you must investigate third-party API footprints, performance ceilings, and how the feature matches your current repository state.

Plaintext

Plain textANTLR4BashCC#CSSCoffeeScriptCMakeDartDjangoDockerEJSErlangGitGoGraphQLGroovyHTMLJavaJavaScriptJSONJSXKotlinLaTeXLessLuaMakefileMarkdownMATLABMarkupObjective-CPerlPHPPowerShell.propertiesProtocol BuffersPythonRRubySass (Sass)Sass (Scss)SchemeSQLShellSwiftSVGTSXTypeScriptWebAssemblyYAMLXML``   RESEARCH: Initialize a separate, isolated sub-agent to investigate what is involved in building [insert project/feature idea].   Instruct the sub-agent to explore separately and output a concise markdown report (`research.md`) covering:  1. Industry Standard Approaches: How this domain problem is typically solved in modern engineering.  2. Trade-offs & Architecture Options: The top 2-3 technical approaches with pros/cons.  3. System Alignment: How this must fit into our existing repository architecture, languages, and dependencies (scan the repo structure first).  4. Critical Failure Modes: The hidden edge cases, security vulnerabilities, or infrastructure bottlenecks inherent to this problem space.  The sub-agent must return ONLY the finalized `research.md` to this main context to prevent token bloat. Do not write any feature code or system designs yet.   ``

📜 Phase 1: Global Governance (The Constitution)
------------------------------------------------

**The Goal:** Establish the project's engineering laws. By anchoring these rules inside CLAUDE.md, Claude Code natively reads and abides by your testing, formatting, and linting standards automatically in every subsequent step.

Plaintext

Plain textANTLR4BashCC#CSSCoffeeScriptCMakeDartDjangoDockerEJSErlangGitGoGraphQLGroovyHTMLJavaJavaScriptJSONJSXKotlinLaTeXLessLuaMakefileMarkdownMATLABMarkupObjective-CPerlPHPPowerShell.propertiesProtocol BuffersPythonRRubySass (Sass)Sass (Scss)SchemeSQLShellSwiftSVGTSXTypeScriptWebAssemblyYAMLXML``   CONSTITUTION: Analyze our tech stack, existing repository structure, and codebase dependencies. Based on modern best practices for this ecosystem and the constraints of our environment, initialize an isolated sub-agent to draft or update our root `CLAUDE.md` file.   This file will serve as our project's absolute architectural and behavioral constitution. It must explicitly document:  1. Build & Test Commands: Exact terminal commands to run the build, execute specific test suites, and run linters.  2. Code Style & Standards: Formatting guidelines, naming conventions (e.g., camelCase vs snake_case), and file structure rules.  3. Architectural Patterns: Strict directory layouts, decoupling rules (e.g., services vs controllers), data validation strategies, and error-handling paradigms.  4. Testing Mandates: Requirements for code coverage, mocking external services, and test file naming conventions.  Ensure the sub-agent writes this directly to `CLAUDE.md` and closes itself, returning only a summary of the development laws established.   ``

📐 Phase 2: The Macro Blueprint (System Architecture)
-----------------------------------------------------

**The Goal:** Solidify the structural architecture of the project. This sets a hard boundary on databases, frameworks, infrastructure topology, and core entities before individual feature scopes are mapped.

Plaintext

Plain textANTLR4BashCC#CSSCoffeeScriptCMakeDartDjangoDockerEJSErlangGitGoGraphQLGroovyHTMLJavaJavaScriptJSONJSXKotlinLaTeXLessLuaMakefileMarkdownMATLABMarkupObjective-CPerlPHPPowerShell.propertiesProtocol BuffersPythonRRubySass (Sass)Sass (Scss)SchemeSQLShellSwiftSVGTSXTypeScriptWebAssemblyYAMLXML``   ARCHITECTURE: Review our `research.md` and our `CLAUDE.md` constitution. Draft a comprehensive `architecture_spec.md` file in the root directory.   This must define the project's macro blueprint:  1. Target Tech Stack: Specific versions of languages, databases, frameworks, and runtime environments.  2. Global Entity & Data Models: Core database schema concepts, relationships, and data primitives.  3. Infrastructure & Boundary Maps: Deployment environments, networking boundaries, caching layers, and external third-party API dependencies (e.g., Stripe, AWS S3).  4. Core Security Posture: Authentication mechanics, authorization patterns, data-at-rest/in-transit encryption standards.  This document must act as the fixed technical ceiling for the project. No feature implementation details yet.   ``

🗂️ Phase 3: Modular Decomposition (Feature Extraction)
-------------------------------------------------------

**The Goal:** Break down the global project scope into an ordered, highly granular backlog. You extract all features here to grasp the macro roadmap, mapping out what dependencies dictate the build sequence.

Plaintext

Plain textANTLR4BashCC#CSSCoffeeScriptCMakeDartDjangoDockerEJSErlangGitGoGraphQLGroovyHTMLJavaJavaScriptJSONJSXKotlinLaTeXLessLuaMakefileMarkdownMATLABMarkupObjective-CPerlPHPPowerShell.propertiesProtocol BuffersPythonRRubySass (Sass)Sass (Scss)SchemeSQLShellSwiftSVGTSXTypeScriptWebAssemblyYAMLXML``   EXTRACT: Read the `architecture_spec.md` and any existing project requirements. Break down the entire project scope into an exhaustive, highly modular list of atomic features.   Generate a `FEATURES_BACKLOG.md` file that organizes these features into a sequential roadmap based strictly on logical dependencies (e.g., Database Setup -> Auth -> Core API -> Third-Party Integrations).   Each extracted feature must be assigned a unique ID (e.g., `FEAT-001`) and include:  - A brief 2-sentence scope description.  - Strict upstream dependencies (what must be built *before* this feature can start).  - A checklist representing its raw functional goals.   ``

📝 Phase 4A: Feature Draft (The Micro Spec)
-------------------------------------------

**The Goal:** Create a targeted behavioral specification for a single, isolated unit of work, pulled from your backlog right before development. This focuses exclusively on expectations and interface schemas.

Plaintext

Plain textANTLR4BashCC#CSSCoffeeScriptCMakeDartDjangoDockerEJSErlangGitGoGraphQLGroovyHTMLJavaJavaScriptJSONJSXKotlinLaTeXLessLuaMakefileMarkdownMATLABMarkupObjective-CPerlPHPPowerShell.propertiesProtocol BuffersPythonRRubySass (Sass)Sass (Scss)SchemeSQLShellSwiftSVGTSXTypeScriptWebAssemblyYAMLXML``   SPECIFY: We are preparing to build [FEAT-XXX: Feature Name]. Read its entry in `FEATURES_BACKLOG.md`, our `architecture_spec.md`, and the `CLAUDE.md` constitution. Spin up an isolated sub-agent to draft a highly focused technical specification file at `docs/specs/FEAT-XXX.md`.   The spec must explicitly document:  1. Feature Goal: The core business value and technical purpose.  2. User Scenarios / User Stories: Concrete paths through the feature.  3. Functional Requirements & API/Data Schemas: Exact route definitions, request/response JSON payloads, and local database mutations.  4. Explicit Boundary Rules & Edge Cases: Explicitly what happens when inputs are invalid, values are empty, or external services time out.  5. Out of Scope: What this feature explicitly will *not* do.  6. Acceptance Criteria: Highly quantitative criteria. Make each requirement so specific that a build ignoring it would visibly and programmatically fail an automated test.  The sub-agent must write this file and return to the main context without generating code.   ``

🤨 Phase 4B: AI Spec Hardening (The Interview)
----------------------------------------------

**The Goal:** Actively eliminate ambiguity. Rather than letting hidden logical gaps turn into bugs during coding, Claude Code interrogates the specification to push it to a deterministic, production-ready state.

Plaintext

Plain textANTLR4BashCC#CSSCoffeeScriptCMakeDartDjangoDockerEJSErlangGitGoGraphQLGroovyHTMLJavaJavaScriptJSONJSXKotlinLaTeXLessLuaMakefileMarkdownMATLABMarkupObjective-CPerlPHPPowerShell.propertiesProtocol BuffersPythonRRubySass (Sass)Sass (Scss)SchemeSQLShellSwiftSVGTSXTypeScriptWebAssemblyYAMLXML``   CLARIFY: Read `docs/specs/FEAT-XXX.md`. Act as an elite, deeply cynical, and hyper-critical Principal Software Architect. Your sole goal is to find logical gaps, unhandled technical edge cases, security oversights, and ambiguities in this feature spec before a developer codes it.   Interview me right here in the terminal, asking exactly one targeted question at a time. Do not write code or summarize your thoughts. Ask your hardest questions about missing state transitions, validation boundaries, or failure modes.   After I respond to a question, modify the `docs/specs/FEAT-XXX.md` file dynamically to reflect the clarified requirement, then ask your next question. Continue this loop until you are 100% confident a junior developer could implement this perfectly without asking a single follow-up question. Say "SPEC IS HARDENED" only when there is absolutely nothing left to misread.   ``

🧪 Phase 4C: Executable Truth (Test Generation)
-----------------------------------------------

**The Goal:** Solidify requirements into programmatically verifiable code. By converting acceptance criteria into failing automated tests before writing production files, you lock down the feature boundaries perfectly.

Plaintext

Plain textANTLR4BashCC#CSSCoffeeScriptCMakeDartDjangoDockerEJSErlangGitGoGraphQLGroovyHTMLJavaJavaScriptJSONJSXKotlinLaTeXLessLuaMakefileMarkdownMATLABMarkupObjective-CPerlPHPPowerShell.propertiesProtocol BuffersPythonRRubySass (Sass)Sass (Scss)SchemeSQLShellSwiftSVGTSXTypeScriptWebAssemblyYAMLXML``   TEST_GENERATE: Now that `docs/specs/FEAT-XXX.md` is verified and hardened, spin up an isolated sub-agent to write the comprehensive unit and integration test suites for this feature.   The sub-agent must:  1. Read the `CLAUDE.md` file to verify the exact testing frameworks, file structure conventions, and directory placements required for this repository.  2. Translate every single Acceptance Criterion and Edge Case defined in `FEAT-XXX.md` into an explicit automated test block.  3. Write these test files into their correct locations in the codebase.  4. Execute the test runner using the exact command defined under the testing section of `CLAUDE.md` to confirm that every newly created test fails gracefully (since no code has been written yet).   The sub-agent must output the terminal logs showing a 100% failure rate across the new tests, then close out. Do not write production code yet.   ``

🏗️ Phase 5: Sequential Execution (The Build)
---------------------------------------------

**The Goal:** Write deterministic production logic. Claude Code steps through the failing tests incrementally, checking its progress against the spec and CLAUDE.md rules until the suite is completely green.

Plaintext

Plain textANTLR4BashCC#CSSCoffeeScriptCMakeDartDjangoDockerEJSErlangGitGoGraphQLGroovyHTMLJavaJavaScriptJSONJSXKotlinLaTeXLessLuaMakefileMarkdownMATLABMarkupObjective-CPerlPHPPowerShell.propertiesProtocol BuffersPythonRRubySass (Sass)Sass (Scss)SchemeSQLShellSwiftSVGTSXTypeScriptWebAssemblyYAMLXML``   BUILD: We are ready to implement [FEAT-XXX: Feature Name]. Look at the failing test suite generated in Phase 4C and the source-of-truth document `docs/specs/FEAT-XXX.md`.   Propose a small, iterative, step-by-step implementation plan to make these tests pass. Review the plan with me first.   Once approved, execute the plan in small increments:  1. Write the minimum production code necessary to satisfy a subset of the tests.  2. Run the test runner locally using the exact command defined in `CLAUDE.md` to watch those specific tests turn green.  3. Ensure all code styling, architectural rules, and linting standards specified in `CLAUDE.md` are strictly enforced at every step.  4. Once all tests for this feature pass flawlessly and no regressions are introduced, automatically execute a localized Git commit labeled with conventional commit syntax matching the feature ID.   ``