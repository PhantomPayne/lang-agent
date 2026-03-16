# Process: Consistency Check

## Purpose
Systematically verify that the current body of feature specifications is
internally consistent—no features contradict each other, no terms are used
with conflicting meanings, and the overall design follows the Core Principles.

## When to Run
- After every batch of features is added to the spec
- Before any feature is moved from `draft` to `accepted`
- At scheduled milestones (e.g. after each major version)

## Participating Agents
| Agent | Role in this process |
|---|---|
| Architect | Leads the review; owns the consistency verdict |
| Spec Writer | Provides the current spec; records all findings |
| Compiler Specialist | Checks for semantic ambiguities and implementation contradictions |
| PM | Tracks open issues; prioritises resolution |

## Steps

### 1. Snapshot (Spec Writer)
The Spec Writer produces a clean snapshot of all `draft` and `accepted` features
with their current spec text. This snapshot is the input to the check.

### 2. Terminology Audit (Spec Writer)
Review every defined term in the spec and verify:
- Each term has exactly one definition
- Each term is used consistently throughout
- No undefined term appears in the spec body

Produce a **terminology issues list**.

### 3. Principle Alignment Check (Architect)
For each accepted or draft feature, verify:
- The feature does not violate any Core Principle
- If a trade-off was made, it is explicitly documented and justified

Produce a **principle alignment issues list**.

### 4. Cross-Feature Interaction Check (Architect + Compiler Specialist)
For every pair of features that can interact at runtime or compile time:
- Describe the interaction explicitly
- Verify the interaction is specified (not left as "implementation-defined"
  unless intentionally so)
- Flag interactions that produce surprising or contradictory results

Produce a **cross-feature interaction issues list**.

### 5. Grammar Consistency Check (Compiler Specialist)
Review the language's formal grammar (if it exists at this stage) and verify:
- No ambiguous productions exist (or ambiguities are explicitly resolved by
  precedence rules)
- Syntax is uniform (similar constructs use similar syntax)
- Reserved keywords do not conflict across features

Produce a **grammar issues list**.

### 6. Triage (PM)
The PM reviews all issues lists and assigns each issue:
- **Severity**: Blocker / Major / Minor
- **Owner**: the agent responsible for proposing a fix
- **Target**: the session in which the fix will be discussed

### 7. Resolution Sessions
For each Blocker and Major issue, schedule a focused design session.
The session follows the standard Feature Design workflow.

### 8. Re-check (Architect)
After all Blocker issues are resolved, the Architect performs a targeted
re-check on the affected sections. Only then can features move to `accepted`.

## Outputs
- Updated spec snapshot with all issues resolved or explicitly deferred
- Updated `docs/feature-inventory.md` with revised status labels

## Success Criteria
- Zero Blocker issues remain open
- All open Major issues are scheduled for resolution
- The Architect signs off on the consistency of the `accepted` feature set
