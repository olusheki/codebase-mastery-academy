### Interactive Elements Reference

**When to read this:** During Phase 3 (writing module HTML) and Phase 4 (compilation).

This document contains the strict code patterns, JSON schemas, and structural blueprints for the browser-based visualization tools. All basic generic elements that do not directly map to complex backend configurations have been removed. Worker agents must adhere to these exact DOM structures to ensure type safety and strict schema convergence.

#### Default Element: The Interactive Codebase Explorer
Every generated course MUST feature a global Interactive Codebase Explorer. This is a collapsible file navigation tree. When the user clicks a specific file node, it must open a dynamically generated, highly detailed summary paragraph explaining exactly what that file does and what it depends on.

**HTML Blueprint:**
```html
<aside id="codebase-explorer">
  <ul class="tree-nav">
    <!-- Worker agents must populate these data attributes with full dependency paragraphs -->
    <li class="file-node" 
        data-dependencies="[Pre-rendered dependency mapping paragraph]" 
        data-responsibilities="[Pre-rendered structural summary paragraph]">
      src/main.ts
    </li>
  </ul>
</aside>
<div id="file-summary-panel">
  <!-- Populated dynamically via JS when a file-node is clicked -->
</div>
```
#### Autonomous Widget Generation
For every complex concept, you must independently evaluate: "Does this concept warrant a custom interactive widget?" If the concept involves dynamic state, algorithms, or data flow, you must automatically generate a custom interactive element (e.g., a data flow animation, state machine toggle) to aid deep comprehension.

JS Micro-State-Machine Blueprint:
```js
// Agents must emit valid, functioning state machine logic for interactive widgets
const stateMachine = {
  currentState: 'INIT',
  states: {
    INIT: { next: 'FETCH_DATA', render: () => updateDOM('Initializing connection...') },
    FETCH_DATA: { next: 'PROCESS', render: () => updateDOM('Fetching packet payload...') },
    PROCESS: { next: 'COMPLETE', render: () => updateDOM('Applying internal state transition...') }
  },
  transition() {
    this.currentState = this.states[this.currentState].next;
    this.states[this.currentState].render();
  }
};
```
3. Code ↔ English Translation Blocks
Every code snippet must feature a side-by-side translation. The left panel displays real code from the project with syntax highlighting, and the right panel contains meticulous line-by-line plain English explaining the execution logic.
```html
HTML Blueprint:
<div class="translation-block">
  <div class="code-panel">
    <pre><code class="language-typescript">...</code></pre>
  </div>
  <div class="english-panel">
    <p class="line-explanation" data-line="1">...</p>
  </div>
</div>
```
4. Message Flow / Data Flow Animation
A step-by-step visualization of data moving between components.
Wiring Constraints: The data-steps attribute is delimited by single quotes. Agents must strictly avoid using apostrophes in labels (or replace them with &apos;) to prevent JSON.parse from failing silently and breaking the animation.
HTML Blueprint:
```html
<div class="flow-animation" data-steps='[{"highlight": "actor-1", "label": "Initial request payload", "packet": true, "from": "1", "to": "2"}]'>
  <div id="flow-actor-1" class="flow-actor">Client</div>
  <div id="flow-actor-2" class="flow-actor">Load Balancer</div>
</div>
```
5. Group Chat Animation
An iMessage/WeChat-style chat showing backend components "talking" to each other. Messages appear one by one with typing indicators.
```html
HTML Blueprint:
<div class="chat-window" id="auth-flow-chat">
  <div class="chat-message" data-actor="middleware">Token validation started...</div>
  <button class="chat-next-btn">Next Step</button>
</div>
```
6. Dashed Jargon Underlining (Glossary Tooltips)
Every complex technical term must be styled with a dashed bottom border, linking to an interactive hover-card displaying its technical definition.
- Enforce Systemic Metaphors: Analogies must strictly map to computer science realities (e.g., comparing an Event Loop to a Message Queue at a post office, not a generic restaurant). Every metaphor must immediately be grounded in exact code variables.
Wiring Constraints (Anti-Clipping Rule): Translation blocks and other containers with overflow: hidden will clip tooltips if positioned improperly. Tooltips MUST use position: fixed, calculate coordinates via getBoundingClientRect(), and append to document.body. Do NOT use position: absolute within the parent container.
HTML/CSS Blueprint:
```html
<span class="jargon-term" data-definition="A function passed as an argument to be executed later in the event loop.">callback</span>
.jargon-term {
  border-bottom: 1px dashed var(--color-accent);
  cursor: pointer;
}
```
7. Hyper-Dense Assessment Quizzes (Scenario-Based)
Basic multiple-choice trivia is banned. Quizzes must focus on scenario-based situational questions, challenging the user with "What would a senior engineer do?"
```html
HTML Blueprint:
<div class="scenario-context-block">
  <p class="scenario-setup">Under heavy concurrent network load, a cache validation fails...</p>
  <div class="quiz-question-block"
       data-explanation-right="Correct. The race condition occurs because..."
       data-explanation-wrong="Incorrect. This transition would cause a deadlock...">
    <!-- Options array here -->
  </div>
</div>
```