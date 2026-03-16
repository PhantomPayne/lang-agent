# Process: Example Generation

## Purpose
Write concrete example programs and functions using proposed language features
to surface missing, ambiguous, or confusing areas in the spec before
implementation begins. Working examples are the most effective way to stress-test
a language design.

## When to Run
- After one or more features reach `draft` status
- As part of the user testing process
- When the Architect suspects a spec section is under-specified

## Participating Agents
| Agent | Role in this process |
|---|---|
| Architect | Writes normative examples; reviews all examples for correctness |
| New User | Writes "newcomer" examples that reflect how a beginner would approach the feature |
| Compiler Specialist | Annotates examples with expected compiler output, errors, and diagnostics |
| Chaos Agent | Writes adversarial and edge-case examples |
| Spec Writer | Integrates approved examples into the spec |

## Steps

### 1. Feature Selection (PM)
PM selects the feature or feature set to be exercised in this round of example
generation. Prefer features that have been recently drafted or have known
ambiguities.

### 2. Canonical Examples (Architect)
For the selected feature(s), the Architect produces:
- A "hello world" example (simplest possible use)
- A realistic use-case example (something a real program would do)
- A composition example (using this feature alongside 2–3 other features)

Each example includes:
- Complete, syntactically valid source code
- Expected behaviour (output, type, compile result)
- A short explanation of what is being demonstrated

### 3. Newcomer Examples (New User)
The New User attempts to write programs that accomplish the same goals as the
canonical examples *without* looking at them first. These reveal:
- Intuitive syntax that does not match the spec
- Missing convenience forms
- Error messages that would confuse a beginner

### 4. Adversarial Examples (Chaos Agent)
The Chaos Agent writes examples designed to break things:
- Maximal nesting / recursion
- Unusual combinations with other features
- Code that looks correct but should be rejected
- Code that looks incorrect but should be accepted
- Extreme edge cases (empty inputs, single-element inputs, maximum sizes)

### 5. Compiler Annotation (Compiler Specialist)
For each example, the Compiler Specialist adds:
- Expected compiler output (type signature, IR snippet if relevant, binary output)
- Expected error messages for the newcomer examples that have mistakes
- Notes on any examples that expose implementation ambiguity

### 6. Gap Analysis (All Agents)
All agents review the full annotated example set and answer:
- "What programs can I *not* write that I would expect to be able to write?"
- "What programs can I write that feel wrong and should not be allowed?"
- "Where did the spec not give me enough information to know what would happen?"

Gap findings are recorded as new issues in the issue tracker.

### 7. Spec Update (Architect + Spec Writer)
For each gap identified:
- Minor gaps: Spec Writer adds clarifying prose or a missing example to the spec
- Major gaps: PM schedules a focused design session

### 8. Publish Examples (Spec Writer)
The Spec Writer publishes approved examples to `examples/` and integrates
normative examples into the spec.

## Outputs
- New files under `examples/` with annotated, runnable code
- Updated spec sections with normative examples and clarifications
- New issues for gaps that require design sessions

## Success Criteria
- Every draft feature has at least one canonical example, one newcomer example,
  and one adversarial example
- All examples have been reviewed and annotated by the Compiler Specialist
- No example produces an "I don't know what should happen here" response from
  the Architect
