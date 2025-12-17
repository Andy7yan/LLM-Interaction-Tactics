# LLM Interaction Tactics
### Workflows for Overcoming Model Constraints

---

## 📖 Manifesto

> "Just as programmers must master programming languages, senior AI workers must master the language of AI—Natural Language."

This repository is not merely a collection of prompts; it is an archive of **AI Literacy** and empirical research into human-AI interaction.

The core philosophy here is **Language as Code**. By treating natural language with the same rigorous structure as software code, we can "orchestrate" the cognitive processes of Large Language Models (LLMs). However, current models are not omnipotent; they are bound by constraints such as token limits, reasoning instability, and memory interference.

This repository provides a set of **"Tactics"**—practical, heuristic strategies designed to navigate these bounds (Bounded Intelligence). By employing structured prompts and engineering-grade workflows, we can mitigate model limitations and achieve high-fidelity outputs.

---

## 🎯 Methodology: Tactics for Constraints

These tactics are derived from observing specific model behaviors and limitations:

* **Constraint: Context Window Limits & "Lost in the Middle"**
    * **Tactic: Recursive Search Strategy.**
        Instead of overloading a single chat window, use a depth-first search (DFS) approach. When encountering complex or unknown concepts, open a new, parallel window to query the specific term. Once the concept is mastered, "return" to the main thread. This method mathematically functions like Bayesian optimization, efficiently finding entry points into new conceptual spaces[cite: 1].
    * **Tactic: Problem Decomposition.**
        Complex problems must be broken down. Do not force the model to solve everything in one turn. Instruct the model to analyze the prompt first, then generate the solution in steps[cite: 1].

* **Constraint: Hallucination & Reasoning Flaws**
    * **Tactic: Explicit Verification.**
        Models struggle to self-correct implicitly. You must explicitly instruct the model to assess the situation and verify its reasoning against established sources for factual tasks, while omitting this for creative tasks to prioritize flow[cite: 15].
    * **Tactic: Human-in-the-Loop Weighting.**
        User input carries higher weight than the model's self-generated history. For critical project constraints, explicitly re-inject the core requirements to prevent them from being "diluted" by the conversation history[cite: 1].

* **Constraint: Identity & Context Confusion**
    * **Tactic: Persona/Context Separation.**
        Strictly distinguish between **Gem Personas** (Task-Specific Expert Roles) and **Personal Context** (General User Data). Never assign a fixed global persona for general interactions; instead, use conditional logic to trigger specific memories only when relevant[cite: 3, 6, 7].

---

## 📂 Repository Structure

This project follows a modular architecture, treating prompts as reusable code components.

```text
LLM-Interaction-Tactics/
├── README.md                  # Project Index & Manifesto
├── tactics/                   # [The Playbook] Workflows & Heuristics
│   ├── recursive-search.md    # The DFS approach to knowledge acquisition
│   ├── parallel-windows.md    # Multi-threading for cognitive tasks
│   └── steering-basics.md     # Persona definition & Adjective modifiers
├── prompt-library/            # [The Arsenal] Modular Prompt Files
│   ├── meta/                  # Meta-Tools (Prompts that write prompts)
│   │   └── instruction4instruction.md
│   ├── academic/              # Research & Deep Reading
│   │   ├── paper-reader-stem.md
│   │   └── knowledge-structuraliser.md
│   ├── coding/                # Programming Assistance
│   │   └── programming-entities.md
│   └── tutors/                # Domain-Specific Tutors
│       └── comp9313-tutor.md
└── insights/                  # [The Theory] Notes on AI Literacy
    └── language-as-code.md    # Natural Language as an engineering interface
