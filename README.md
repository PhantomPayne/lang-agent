# lang-agent

A structured system of AI agents, processes, and skills for collaborative
programming language design. The goal is not to build a language immediately—
it is to set up the conversations, workflows, and artefacts that will lead to
a complete, coherent, and delightful language specification.

---

## Repository Layout

```
lang-agent/
├── agents/               # Agent definitions (who they are and what they do)
├── processes/            # Step-by-step design workflows
├── skills/               # Reusable capabilities used by agents
├── docs/                 # Living design documents produced by the team
│   ├── core-principles.md
│   ├── feature-inventory.md
│   ├── testing/          # Per-feature user testing reports
│   └── dx-brainstorm/    # Notes from DX brainstorm sessions
└── examples/             # Annotated code examples per feature
```

---

## Agents

Each agent is defined in `agents/<name>.yaml`. An agent definition includes
its role, a detailed system prompt for an LLM, the skills it uses, and the
triggers that determine when it participates.

| Agent | File | Primary responsibility |
|---|---|---|
| **PM** | `agents/pm.yaml` | Process stewardship, facilitation, backlog management |
| **Architect** | `agents/architect.yaml` | Language consistency, principle alignment, cross-feature analysis |
| **Compiler Specialist** | `agents/compiler-specialist.yaml` | Implementability, type systems, error messages |
| **Tooling Master** | `agents/tooling-master.yaml` | IDE support, formatters, debuggers, LSP |
| **New User** | `agents/new-user.yaml` | Beginner perspective, documentation gaps, onboarding |
| **Evangelist** | `agents/evangelist.yaml` | Narrative, tutorials, community engagement |
| **Chaos Agent** | `agents/chaos-agent.yaml` | Wild ideas, assumption challenges, edge cases |
| **Spec Writer** | `agents/spec-writer.yaml` | Precise written specifications, terminology, changelog |
| **Security Advisor** | `agents/security-advisor.yaml` | Vulnerability patterns, safe-by-default design |

---

## Processes

Processes are step-by-step workflows that coordinate agents toward a specific
outcome. Each process document defines which agents participate, the steps to
follow, the expected outputs, and success criteria.

| Process | File | When to run |
|---|---|---|
| **Core Principles** | `processes/core-principles.md` | Once, at project start |
| **Feature Spec Identification** | `processes/feature-spec-identification.md` | After Core Principles; revisited at milestones |
| **Consistency Check** | `processes/consistency-check.md` | After each batch of features; before acceptance |
| **Example Generation** | `processes/example-generation.md` | After features reach `draft` status |
| **User Testing** | `processes/user-testing.md` | After examples exist; before `accepted` |
| **DX Brainstorm** | `processes/dx-brainstorm.md` | Once per milestone; triggered by DX issues |

---

## Skills

Skills are reusable, well-defined capabilities that agents invoke during
processes. They produce structured output that feeds into the next step.

| Skill | File | Used by |
|---|---|---|
| **Principle Alignment** | `skills/principle-alignment.yaml` | Architect, PM |
| **Spec Consistency Review** | `skills/spec-consistency-review.yaml` | Spec Writer, Architect |
| **Beginner Perspective** | `skills/beginner-perspective.yaml` | New User |
| **Implementability Assessment** | `skills/implementability-assessment.yaml` | Compiler Specialist |
| **DX Audit** | `skills/dx-audit.yaml` | Tooling Master, New User, Evangelist |
| **Lateral Thinking** | `skills/lateral-thinking.yaml` | Chaos Agent |

---

## Recommended Starting Sequence

1. **Run Core Principles** — `processes/core-principles.md`
   All agents participate. Output: `docs/core-principles.md`

2. **Run Feature Spec Identification** — `processes/feature-spec-identification.md`
   All agents participate. Output: `docs/feature-inventory.md`

3. **For each MVL feature** (repeat until complete):
   a. **Design session** — Architect leads; all agents review
   b. **Consistency Check** — `processes/consistency-check.md`
   c. **Example Generation** — `processes/example-generation.md`
   d. **User Testing** — `processes/user-testing.md`
   e. Feature is moved to `accepted`

4. **DX Brainstorm** — `processes/dx-brainstorm.md`
   Run after every 3–5 features are accepted.

5. **Repeat** from step 3 until all MVL features are `accepted`.

---

## Design Documents

| Document | Status | Description |
|---|---|---|
| `docs/core-principles.md` | 🔴 Not started | The language's fundamental values |
| `docs/feature-inventory.md` | 🔴 Not started | All features with labels and dependencies |

---

## Contributing

To add a new agent:
1. Create `agents/<name>.yaml` following the schema of existing agents
2. List the skills the agent uses under `skills:`
3. Add the agent to the table in this README
4. Update any process files that should include the agent

To add a new process:
1. Create `processes/<name>.md` following the structure of existing processes
2. Add the process to the table in this README

To add a new skill:
1. Create `skills/<name>.yaml` following the schema of existing skills
2. Add the skill to the table in this README
3. Reference it in the `skills:` list of any agents that use it
