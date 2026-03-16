# Process: Feature Spec Identification

## Purpose
Determine the complete set of feature specifications needed before a language
implementation can begin. This is not about designing every feature in detail—
it is about mapping the territory so nothing critical is overlooked.

## When to Run
- After Core Principles are established
- Revisited whenever a major new domain is added to the language's scope

## Participating Agents
| Agent | Role in this process |
|---|---|
| PM | Facilitates; maintains the master feature list |
| Architect | Ensures the feature map is coherent; identifies structural dependencies |
| Compiler Specialist | Flags features that require compiler support to be viable |
| Tooling Master | Identifies features that unlock or require tooling |
| New User | Identifies features a new user would expect from day one |
| Chaos Agent | Proposes features the team hasn't considered yet |
| Spec Writer | Produces the formal feature list document |

## Steps

### 1. Taxonomy Seeding (Architect)
The Architect produces a high-level taxonomy of language feature categories,
for example:
- Type system (primitives, composites, generics, type inference, …)
- Memory model (ownership, borrowing, GC, arenas, …)
- Concurrency model (threads, async/await, actors, CSP, …)
- Module and package system
- Error handling
- Metaprogramming / macros
- Standard library surface area
- Build and deployment model
- Interoperability (FFI, platform APIs, …)

### 2. Completeness Brainstorm (All Agents — parallel)
Each agent independently expands each category with specific features they
consider essential or highly desirable. Agents submit their lists without
seeing each other's lists first to avoid anchoring.

### 3. Merge and Deduplicate (PM + Spec Writer)
PM and Spec Writer merge all lists into a single master feature inventory.
Duplicates are collapsed; conflicts are flagged for discussion.

### 4. Dependency Mapping (Architect + Compiler Specialist)
For each feature, identify:
- **Prerequisite features**: features that must exist before this one can be specified
- **Blocking features**: features that cannot be fully designed until this one is stable
- Produce a dependency graph (even if informal)

### 5. Coverage Check Against Core Principles (Architect)
For each Core Principle, verify that at least one feature in the list directly
supports it. Flag any principle that has no corresponding feature—either the
principle implies a missing feature, or the principle needs re-examination.

### 6. MVP Scoping (PM)
Working with the dependency graph, the PM proposes a Minimum Viable Language (MVL)
feature set: the smallest coherent subset that allows real programs to be written
and a first compiler to be built.

Features are labelled:
- `mvl` — required for Minimum Viable Language
- `v1` — targeted for initial public release
- `future` — desirable but deferred
- `speculative` — interesting but not yet committed

### 7. Publish (Spec Writer)
The Spec Writer publishes the feature inventory to `docs/feature-inventory.md`.

## Outputs
- `docs/feature-inventory.md` — master feature list with labels, dependencies, and owners

## Success Criteria
- Every feature has an owner (an agent or human responsible for driving its design)
- The MVL set is small enough to implement in a reasonable timeframe
- The dependency graph has no cycles
- Every Core Principle is supported by at least one MVL feature
