# Codebase Mastery Academy: The "Detail Machine"

**An uncompromising, university-grade architectural deep dive system.**

The Codebase Mastery Academy is a multi-agent orchestration skill designed to ingest an entire repository and output an exhaustive, interactive HTML course. It actively rejects abstracted LLM summarization, hand-waving, and forced beginner metaphors in favor of uncompromising technical truth, deep dependency mapping, and rigorous testing analysis.

---

## Purpose

Standard LLM codebase interactions often suffer from token bloat, leading to lazy summaries and generic explanations. This skill was architected to act as an "Obsessive Detail Machine."

Its primary directives are to:

* **Trace Every Dependency:** Read every file, check every edge case, and explain the exact backend mechanics.
* **Expose the Truth:** Discard generic metaphors and teach using pure, high-level computer science vocabulary.
* **Never Truncate Code:** Present 1:1 line-by-line execution logic tracing alongside untruncated source code.

## Compatibility and Invocation

This skill is optimized for **Antigravity 2.0**, operating as a multi-agent Supervisor-Worker pipeline. It relies on a Lead Architect to dispatch micro-payloads to specialized worker agents. However, the schema constraints and chunk-boundary rules make it portable to other advanced AI agent frameworks that support multi-step planning and sub-agent orchestration.

**How to Invoke (Antigravity 2.0):**
Invoke the skill by assigning the Lead Architect to your target repository. You must provide the root directory of the codebase you wish to analyze.

Example execution pattern:
`ag run codebase-mastery-academy --target ./path/to/local/repository`

Once invoked, the Lead Architect will autonomously assume control, read the project configuration, and begin the Map-Reduce parsing phases without further human intervention.

## How It Works: Execution Workflow

The system prevents LLM context degradation by refusing to ingest the codebase in a single pass. Instead, it executes a rigorous, multi-phase pipeline:

1. **Initial Assessment (Phase 0 - Architecture Analyzer):** The system scans the directory topology, package manifests, and configuration files to extract foundational technologies, operational trade-offs, and critical language syntax nuances.
2. **Implementation Planning (Phase 1 - Logical Sequencer):** Using a Map-Reduce pattern, the agent maps the global architecture. It dynamically drafts a course implementation plan, calculating exactly how many core modules and sub-modules are required to comprehensively cover the repository. It defines the optimal non-linear learning sequence.
3. **Deep Granular Analysis (Phase 2 - Mechanical Translator):** The Lead Architect dispatches strict 4,000-line micro-payloads to the translator agents. These agents generate full, untruncated code syntax explanations and meticulous execution logic tracing.
4. **Reliability Auditing (Phase 3 - Reliability Evaluator):** Agents parse unit, integration, and end-to-end tests to expose verification strategies, edge cases, and regression protections.
5. **Compilation (Phase 4 - UI Orchestrator):** The system compiles the generated payloads into a university-grade interactive DOM, injecting custom state-machine logic and interactive widgets where appropriate.

## Dynamic Course Structure

The skill dynamically scales the course to fit the codebase, but it enforces a strict mandatory framework for the output:

* **Module 0: Prerequisites.** A deep dive into the specific technologies, memory lifetimes, advanced type constraints, and unique syntax required to understand the target codebase.
* **Core Modules (Dynamic Count):** The number of core modules is dynamically generated based on the Phase 1 implementation plan. These modules trace every discernible feature non-linearly, chasing all dependencies to explain architectural design choices.
* **Penultimate Module: Testing & Edge Cases.** A meticulous breakdown of all test files, exposing what they verify, how the CI/CD pipeline thinks, and the specific regression vectors the system defends against.

## Interactive Output Features

The UI Orchestrator generates a bespoke frontend designed for advanced code comprehension:

* **The Interactive Codebase Explorer:** A persistent, collapsible file navigation tree. Clicking any file node dynamically opens a highly detailed summary explaining exactly what that file does and what it depends on.
* **Autonomous Widget Generation:** The system evaluates concepts on the fly. If a concept involves dynamic state, algorithms, or data flow, it autonomously generates custom interactive elements (e.g., data flow animations, state machine toggles).
* **Untruncated Translation Blocks:** A side-by-side UI where the left panel displays exact, untruncated code, and the right panel explains the execution logic line-by-line.
* **Dashed Jargon Underlining:** Every piece of technical jargon is underlined and links to an interactive hover-card defining the concept.
* **Rigorous Comprehension Checks:** Modules end with exhaustive FAQs and "Grilling Quizzes"—scenario-based debugging questions that force the user to synthesize deep system understanding rather than basic trivia.

---

### Credits

Concept and architecture by Daniel Olusheki (https://github.com/olusheki).
Inspiration and Code Assets from https://github.com/zarazhangrui/codebase-to-course 