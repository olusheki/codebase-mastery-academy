### Gotchas — Common Failure Points

**When to read this:** During Phase 3 (writing module HTML) and Phase 4 (review).
This document serves as a strict structural ledger tracking systemic AI failure states, laziness trends, and formatting edge cases to preemptively block model short-circuiting.

#### Code Modifications
Trimming, simplifying, or "cleaning up" code snippets from the codebase is strictly prohibited. You must never use empty abstract placeholders (e.g., `// TODO: Implement the rest...`). Code logic must be presented fully and untruncated. Skipping minor files or abstracting code paths will trigger an immediate hard failure. To resolve UI layout conflicts without truncating, mandate that untruncated code blocks use an interactive wrapping structure or a "Show full file" toggle.

#### 1. Code-Hunk Truncation & Abstract Placeholders [HARD FAILURE]
Trimming, simplifying, or "cleaning up" code snippets from the codebase is strictly prohibited. You must never use empty abstract placeholders (e.g., `// TODO: Implement the rest...`). Code logic must be presented fully and untruncated. Skipping minor files or abstracting code paths will trigger an immediate hard failure.

#### 2. Soft Hand-Waving of Verification Blocks [HARD FAILURE]
Do not gloss over unit, integration, or end-to-end tests with high-level summaries. You must explicitly expose the underlying verification strategies, mocking mechanics, and precise regression vectors the system protects against. Soft hand-waving of verification blocks is banned.

#### 3. Context Window Overload & Performance Degradation
Do not force subagents to ingest entire directories or cross performance-degradation safety lines. You must respect the strict 4,000-line chunk boundary limit dispatched by the Lead Architect. Pushing past micro-context limits causes LLM laziness and context degradation, which destroys the architectural precision of the output.

#### 4. Recycled Metaphors
Using "restaurant" or "kitchen" analogies for everything is banned. Discard all generic metaphors. If you use a metaphor, it must feel inevitable for that specific concept. Otherwise, state advanced engineering concepts using pure, high-level computer science vocabulary.

#### 5. Trivia-Based Quizzes
Asking "What does API stand for?" or "Which file handles X?"—those test recall, not understanding. Basic multiple-choice trivia is banned. Every quiz must feature hyper-dense, scenario-based debugging questions (e.g., identifying race conditions or pinpointing state transition failures under concurrent network load).

#### 6. Missing Interactive Elements & Abstracted Logic
Do not output a module with only text and code blocks. Every technical layer must be evaluated by the Custom Interactivity Evaluator. If a bespoke custom widget (like an interactive state transition simulator or packet data tracker) is warranted, you must emit the exact, fully valid micro-state-machine HTML/JS logic to build it without taking shortcuts.

#### 7. Tooltip Clipping
Translation blocks use `overflow: hidden` for code wrapping. If tooltips use `position: absolute` inside the term element, they get clipped by the container. **Fix:** Tooltips must use the native HTML `<dialog>` element or the native CSS Anchor Positioning API. This prevents the UI from breaking when the user scrolls or resizes the browser window mid-hover.