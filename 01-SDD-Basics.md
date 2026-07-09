# Mastering Specification-Driven Development (SDD) for AI Orchestration

### 1. Conceptual Hook & Blueprint

**The "Why"**
Most developers treat AI like a faster pair of hands, asking it to "write code" immediately. This often leads to "Architectural Debt"—a messy pile of code that works today but breaks tomorrow. **Specification-Driven Development (SDD)** flips the script. Instead of telling the AI what to *write*, you tell it how to *think*. By treating specifications as the "Source of Truth," you move from being a coder to a **System Engineer**. This ensures your projects are scalable, bug-resistant, and perfectly aligned with professional standards before a single line of logic is ever written.

**Roadmap**
In this guide, we will walk through the SDD lifecycle:
*   **The Foundation:** Researching and setting the "Laws of the Repo."
*   **The Structural Map:** Designing the macro and micro architecture.
*   **The Safety Net:** Hardening logic and creating "Executable Truth" (Tests).
*   **The Build:** Incremental execution and final delivery.

---

### 2. The Learning Journey

#### Step 1: The Technical Scout (Discovery & Research)
**The Core Concept:** Before building, you must understand the landscape. This step uses an AI "sub-agent" to act as a specialized researcher, checking if your idea is actually feasible and what industry standards already exist. It prevents you from reinventing the wheel poorly.

**Real-World Example:** Imagine you want to build a deck on your house. Before buying wood, a "scout" would check the local building codes, the soil stability, and what materials your neighbors used. You wouldn't just start digging.

**🧠 Brainstorming Milestone:** If you were building a "Secure File Sharing App," what is one "Critical Failure Mode" (a way the system could break) that a research sub-agent should look for?

#### Step 2: Drafting the Constitution (Global Governance)
**The Core Concept:** Every project needs a set of rules. In Claude Code, this lives in a `CLAUDE.md` file. This "Constitution" tells the AI exactly how to name files, how to handle errors, and what commands to run. It ensures the AI doesn't "hallucinate" its own style.

**Real-World Example:** Think of this as the "Brand Guidelines" for a company. It ensures that whether a designer in New York or London makes a flyer, the colors and logos look exactly the same.

**🧠 Brainstorming Milestone:** Why is it better to tell the AI the "Code Style" rules *before* it starts writing features rather than correcting the style afterward?

#### Step 3: The Macro Blueprint (System Architecture)
**The Core Concept:** This is where you define the boundaries. You aren't deciding what the "Login Button" looks like; you are deciding which database you use and how the data flows between the front end and the back end.

**Real-World Example:** In a city, the Macro Blueprint is the zoning map. It decides where the residential, industrial, and commercial zones go. It doesn't decide what color a specific house is painted—just where the house is allowed to be.

**🧠 Brainstorming Milestone:** Look at your favorite app (like Spotify or Instagram). Can you name one "3rd-party API dependency" they likely have in their architecture?

#### Step 4: Modular Decomposition (The Backlog)
**The Core Concept:** Complexity is the enemy of progress. Decomposition takes your massive "Macro Blueprint" and breaks it into "Atomic Units"—small, manageable features that can be built one by one without breaking the whole system.

**Real-World Example:** If you are building a car, you don't build "a car" all at once. You build the engine, then the transmission, then the wheels. Each is a separate task on the assembly line.

**🧠 Brainstorming Milestone:** If you are building an e-commerce store, which feature must be finished first: the "Checkout System" or the "Product Database"? Why?

#### Step 5: The Micro-Spec & The AI Interview (Hardening)
**The Core Concept:** For every small feature, you create a mini-contract. You then invite the AI to act as a "Hyper-critical Architect" to find flaws in your logic. This "AI Interview" forces you to think about edge cases (like "What happens if the user enters a negative number?") before coding starts.

**Real-World Example:** This is like a lawyer cross-examining a witness. The goal is to find the "holes" in the story before it goes to trial.

**🧠 Brainstorming Milestone:** Think of a "Password Reset" feature. What is one "User Scenario" or "Edge Case" that could go wrong if the spec isn't clear?

#### Step 6: Executable Truth (TDD Generation)
**The Core Concept:** Test-Driven Development (TDD) means writing the "grading key" before the "exam." You generate automated tests that *fail* on purpose because the feature doesn't exist yet. This ensures that when you finally write code, you know exactly when it’s "correct."

**Real-World Example:** Imagine a puzzle box. The "Test" is the empty shape in the box. The "Code" is the puzzle piece. If the piece doesn't fit the shape perfectly, it’s not finished.

**🧠 Brainstorming Milestone:** If a test passes *before* you've written any code, what does that tell you about your testing environment?

#### Step 7: Sequential Execution (The Build)
**The Core Concept:** Now, and only now, do you write production code. You build one tiny piece at a time, checking it against your failing tests until they all turn green. This is called "Refining the logic" until it meets the spec.

**Real-World Example:** This is like building a LEGO set using the manual. Because you have the instructions (Spec) and you can see if the pieces fit (Tests), you can build a complex castle without any guesswork.

**🧠 Brainstorming Milestone:** You’ve finished the code and all tests pass! Why should you still run a "Linting" or "Style" check before you consider the job done?

---

### 3. Hands-On Practical Application

Ready to put SDD into practice? Choose a project level below to begin your journey.

| Project Level | Task | Key Focus |
| :--- | :--- | :--- |
| **Project 1: Beginner** | **The "Smart" Unit Converter** | Use SDD to build a tool that converts units (Weight, Temp). Focus on **Phase 1 (Constitution)** to ensure the AI uses a specific naming convention. |
| **Project 2: Intermediate** | **The Personal Expense Tracker** | Use SDD to create a tool with a database. Focus on **Phase 4B (The AI Interview)** to find logic gaps in how expenses are categorized or deleted. |
| **Project 3: Advanced** | **Multi-User Task Orchestrator** | Build a system with Auth and real-time updates. Focus on **Phase 4C (TDD)** to ensure the system handles multiple users trying to edit the same task simultaneously. |
