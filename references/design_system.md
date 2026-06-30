### Design System & DOM Dictionary

**When to read this:** During Phase 3 and Phase 4 (UI Orchestration).
You are strictly forbidden from writing inline CSS (`style="..."`) or hallucinating custom CSS classes. You must exclusively use the structural HTML/CSS patterns defined below, which perfectly map to the course's underlying `styles.css`.

#### 1. Core Layout & Typography
* **Module Container:** Every major section must be wrapped in `<section class="module" id="module-[id]">`.
* **Content Wrapper:** Inside the module, wrap content in `<div class="module-content">`.
* **Headers:** * `<h2 class="module-title">` for the main module title.
  * `<h3 class="screen-heading">` for internal section breaks.
* **Text Limits:** Paragraphs `<p>` should be detailed and uncompromising. 
* **Scroll Animations:** Add the class `.animate-in` to any element (paragraphs, widgets, translation blocks) to trigger scroll-reveal animations. For lists or cards, wrap them in `<div class="stagger-children">` and give each child `.animate-in`.

#### 2. Callout Boxes
Use these for edge cases, warnings, or foundational principles.

```html
<div class="callout callout-accent animate-in">
  <div class="callout-icon">💡</div>
  <div class="callout-content">
    <span class="callout-title">Architectural Decision</span>
    <p>Detailed explanation goes here.</p>
  </div>
</div>
```

Variants: callout-accent (Insights), callout-info (Context/Blue), callout-warning (Red/Gotchas).

3. Pattern / Feature Cards
Use these when breaking down multiple related concepts, architectures, or system traits.

```HTML
<div class="pattern-cards stagger-children">
  <div class="pattern-card animate-in">
    <div class="pattern-icon">🔄</div>
    <h4 class="pattern-title">Event Loop</h4>
    <p class="pattern-desc">Detailed explanation of the async loop...</p>
  </div>
  </div>
```

4. Inline Code & Badges
Inline variables: Wrap in standard.

Configuration / Dependency Lists: Use the .badge-list structure to show what a specific file imports or depends on.

```HTML
<div class="badge-list animate-in">
  <div class="badge-item">
    <span class="badge-code">import { x } from 'y';</span>
    <span class="badge-desc">Why this dependency is critical to the architecture.</span>
  </div>
</div>
```

5. Visual File Trees
When mapping directory topology (Phase 0/1 output), use this structure:

```HTML
<div class="file-tree animate-in">
  <div class="ft-folder">
    <span class="ft-name">src/core/</span>
    <span class="ft-desc">Handles state synchronization</span>
    <div class="ft-children">
      <div class="ft-file">
        <span class="ft-name">engine.ts</span>
        <span class="ft-desc">The primary event loop mechanism.</span>
      </div>
    </div>
  </div>
</div>
```

6. Tooltips (Glossary)
Every technical term must use this exact structure to avoid container clipping.

```HTML
<span class="term" data-definition="Meticulous 1-2 sentence plain-English definition here.">Your Jargon</span>
```
