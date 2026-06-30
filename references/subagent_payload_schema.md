### Subagent Payload Schema Reference

**When to read this:** This document defines the strict data contract used by the Lead Architect to establish micro-context boundaries and dispatch task payloads to worker subagents.

All narrative-driven "Teaching Arc" prompts, soft hooks, and beginner metaphors have been stripped from the system. Worker agents must exclusively receive and emit data adhering to the following pure architectural payload schemas.

#### 1. The Input Payload Envelope (XML Boundaries)
To prevent prompt degradation, context drift, and tool overtriggering, the Lead Architect must dispatch tasks using strict XML structural boundaries. This ensures type safety and exact schema convergence across the subagent network.

```xml
<worker_payload>
    <task_metadata>
        <assigned_phase>Phase 2: Mechanical Translator</assigned_phase>
        <!-- Enforces the strict context boundary to prevent LLM laziness -->
        <chunk_boundary_limit>4000</chunk_boundary_limit>
        <is_pre_extracted_brief>true</is_pre_extracted_brief>
    </task_metadata>

    <module_brief>
        <teaching_arc>Focus on the race conditions during memory allocation.</teaching_arc>
        <required_widgets>interactive-state-machine</required_widgets>
    </module_brief>
    
    <code_context>
        <!-- Line-number bounds for untruncated code payloads. TRUNCATION IS A HARD FAILURE. -->
        <file path="src/core/engine.ts" start_line="1" end_line="450" />
        
        <exact_syntax_references>
            <!-- Target specific methods, state transitions, or memory lifecycles -->
            <reference>State synchronization loop in init()</reference>
        </exact_syntax_references>
    </code_context>

    <reliability_context>
        <dependent_testing_pathways>
            <!-- Map exact test files verifying this module -->
            <pathway>tests/core/engine.spec.ts</pathway>
        </dependent_testing_pathways>
    </reliability_context>
</worker_payload>
```

2. The Output Generation Schema (JSON Contract)
When worker agents complete their phase, they must serialize their findings into this strict JSON contract before handing it off to the Phase 4 UI Orchestrator.
Failure to populate the 5 mandatory technical FAQs or the use of abstract placeholders (e.g., // TODO: add code here) will trigger an immediate pipeline failure.

```json
{
  "module_node_id": "core-engine",
  "structural_summary": "Definitive paragraph defining exact system responsibilities and technical dependencies for the Interactive Codebase Explorer.",
  "untruncated_code_payloads": [
    {
      "file_path": "src/core/engine.ts",
      "bounds": {"start_line": 12, "end_line": 85},
      "raw_code": "...[EXACT CODE - NO TRUNCATION]...",
      "mechanical_translation": "Meticulous 1:1 line-by-line execution logic tracing."
    }
  ],
  "reliability_and_testing": {
    "test_vectors": ["What specific edge cases are verified in the test suite..."],
    "regression_states_protected": ["Exact regression vectors the system defends against..."]
  },
  "mandatory_technical_faqs": [
    {
      "question": "Scenario-based debugging question (e.g., 'If this specific state transition fails under concurrent network load, which line must be patched?').",
      "answer": "Uncompromising high-level explanation with dashed jargon underlining applied."
    },
    // MUST contain exactly 5 edge-case-driven technical FAQs per module payload
    {}, {}, {}, {}
  ],
  "custom_interactivity_widgets": [
    {
      "widget_type": "state-machine-simulator",
      "html_js_logic": "...[Valid micro-state-machine toggles emitted by the Interactivity Evaluator]..."
    }
  ]
}
```