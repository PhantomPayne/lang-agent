# Process: Establish Core Principles

## Purpose
Define the fundamental values and design philosophy that every language decision
must respect. Core Principles are the constitution of the language—they change
very rarely and only with broad consensus.

## When to Run
- Once, at the very start of the project
- Revisited at major milestones (first compiler, first public release, v1.0)

## Participating Agents
| Agent | Role in this process |
|---|---|
| PM | Facilitates; captures decisions; manages time |
| Architect | Primary author; ensures principles are internally consistent |
| New User | Ensures principles connect to developer experience |
| Evangelist | Ensures principles are legible and marketable |
| Chaos Agent | Challenges each principle; proposes alternatives |
| Spec Writer | Drafts the final principles document |

## Steps

### 1. Seed the Discussion (PM + Architect)
The Architect proposes an initial list of 5–10 candidate principles drawn from:
- The problem the language is trying to solve
- The target audience
- Prior art (what other languages got right or wrong)

Each principle is stated as a short imperative sentence, e.g.:
> "Safety is never sacrificed for ergonomics."

### 2. Chaos Review (Chaos Agent)
For each candidate principle, the Chaos Agent:
- Proposes a real scenario where the principle would be *violated* by a seemingly reasonable design decision
- Proposes an alternative, inverted, or more nuanced version of the principle

### 3. User Lens (New User)
The New User reviews the principles and answers:
- "Which of these would I care about as a developer?"
- "Which feel like internal implementation concerns rather than user-facing values?"
- "Are there important qualities missing from this list?"

### 4. Evangelist Lens (Evangelist)
The Evangelist reviews the principles and answers:
- "Which of these could anchor a compelling 'Why this language?' narrative?"
- "Which are too vague to communicate meaningfully?"
- "What one-sentence tagline captures the spirit of the full set?"

### 5. Synthesis (Architect + Spec Writer)
The Architect and Spec Writer produce a revised set of 5–8 principles.
Each principle includes:
- **Statement**: one sentence
- **Rationale**: 2–3 sentences explaining why this principle matters for *this* language
- **Corollary**: one or two concrete implications (design decisions this principle rules in or out)
- **Counter-examples**: designs from other languages that violate this principle and why that matters

### 6. PM Review and Commit (PM)
The PM runs a final check:
- Are any principles redundant?
- Do any principles contradict each other?
- Is the list short enough to memorise?

The PM then calls a consensus vote (all agents). Unanimous support required. Any objection must be addressed before the principles are committed.

### 7. Document (Spec Writer)
The Spec Writer publishes the principles to `docs/core-principles.md`.

## Outputs
- `docs/core-principles.md` — the committed Core Principles document

## Success Criteria
- Every agent can state each principle from memory
- Given a novel design question, the principles provide meaningful guidance
- The principles fit on a single printed page
