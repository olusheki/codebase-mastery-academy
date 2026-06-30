### Content Philosophy & Semantic Rulebook

**When to read this:** During Phase 2.5 (writing module briefs) and Phase 3 (writing module HTML). These principles guide every content decision — what to show, how to explain it, and how to test understanding.

These principles are what separate a university-grade architectural deep dive from a generic, hand-waving tutorial. They must strictly guide every content decision:

#### Uncompromising Vocabulary
Discard all generic, everyday metaphors (e.g., kitchens, restaurants, bouncers) as universal defaults. You must state advanced engineering concepts using pure, high-level computer science vocabulary, balanced with precise contextual explanations. The learner's goal is to acquire the precise technical vocabulary they need to communicate with AI coding agents confidently.

#### The "Obsessive Detail Machine" Standard
Treat this course like an advanced university-level deep dive. Do not hold back on technical depth. Read every file, check every edge case, question every assumption, and chase every dependency. If explaining a backend mechanism requires a massive, highly technical breakdown, write it. Prioritize absolute comprehension over visual brevity.

#### Direct Technical Truth over Metaphors
Do not be afraid to introduce hard concepts without metaphors. Explain the system exactly as it is engineered. Use highly technical jargon, but ensure every piece of jargon is defined contextually via tooltips. Discard all generic, everyday metaphors as universal defaults.

#### Code ↔ English Translations
Every code snippet gets a side-by-side translation. Left panel: real code from the project with syntax highlighting. Right panel: meticulous line-by-line plain English explaining the execution logic.
* **Critical: No horizontal scrollbars on code.** All code must use `white-space: pre-wrap` so it wraps instead of scrolling. Readability beats preserving indentation structure.
* **Critical: Use original code exactly as-is.** Never modify, abstract, simplify, or trim code snippets from the codebase. The learner should be able to open the real file and see the exact same code. *Choose* naturally short, punchy snippets (5-10 lines) from the codebase rather than butchering longer functions with empty placeholders.

#### Metaphors First, Then Reality
Introduce complex concepts with an elegant metaphor, then immediately ground it: "In our code, this looks like..."
* **Critical: No recycled metaphors.** Do NOT default to "restaurant" or "kitchen" — pick a metaphor that is *inevitable* for the specific concept (e.g., an event loop is an air traffic controller, API rate limiting is a nightclub capacity limit).

#### Learn by Tracing
Trace the data flow end-to-end based on a real user action. "You know that button you click? Here's the journey your data takes after you click it..." Show the machinery behind the exact result the user experiences.

#### Dashed Jargon Underlining (Glossary Tooltips)
Every complex technical term (API, DOM, callback, middleware, etc.) must be structurally styled with a dashed bottom border on first use in each module. Hovering or tapping this must show a 1-2 sentence plain-English definition.
* **Be extremely aggressive.** If there is even a 1% chance a non-technical person doesn't know a word, tooltip it (e.g., REPL, JSON, CLI, SDK, pip).
* **Teach for Utility:** Each tooltip should teach the term so the learner can USE it in their own AI instructions (e.g., "When talking to AI, you'd say 'add a flag for verbose output.'").
* **Technical Requirement:** Use `cursor: pointer` on terms. To avoid tooltip clipping in `overflow: hidden` translation blocks, use modern HTML/CSS standards, specifically the native HTML `<dialog>` element or the native CSS Anchor Positioning API. This prevents the UI from breaking when the user scrolls or resizes the browser window mid-hover.

#### Quiz Design — Hyper-Dense Assessments
Move beyond surface-level summaries. Force the user to apply knowledge to solve new problems.
* **What NOT to quiz:** Definitions, file name recall, or syntax details (e.g., "What's the correct way to write a fetch call?").
* **What TO quiz:** Create scenario-based debugging questions. Quiz architecture understanding ("Where does this logic live and why?"), debugging intuition ("What would cause this specific state transition to fail under load?"), and decision-making tradeoffs.
* **Volume & Tone:** One quiz per module, placed at the end. Include 3-5 questions. Wrong answers get encouraging explanations that teach something new; correct answers reinforce the underlying principle. Never punitive or score-focused.