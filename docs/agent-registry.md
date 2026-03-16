# Agent Registry

> **Maintained by**: HR Agent
> **Updated**: after every process run (evidence) and every 3–5 runs (full evaluation)

This document is the single source of truth for agent health. It records the
effectiveness metrics for every agent and skill, the evidence gathered from
each process run, and the history of improvements applied.

---

## Roster

| Agent | File | Health | Last Evaluated |
|---|---|---|---|
| PM | `agents/pm.yaml` | ⬜ Not yet evaluated | — |
| Architect | `agents/architect.yaml` | ⬜ Not yet evaluated | — |
| Compiler Specialist | `agents/compiler-specialist.yaml` | ⬜ Not yet evaluated | — |
| Tooling Master | `agents/tooling-master.yaml` | ⬜ Not yet evaluated | — |
| New User | `agents/new-user.yaml` | ⬜ Not yet evaluated | — |
| Evangelist | `agents/evangelist.yaml` | ⬜ Not yet evaluated | — |
| Chaos Agent | `agents/chaos-agent.yaml` | ⬜ Not yet evaluated | — |
| Spec Writer | `agents/spec-writer.yaml` | ⬜ Not yet evaluated | — |
| Security Advisor | `agents/security-advisor.yaml` | ⬜ Not yet evaluated | — |
| HR Agent | `agents/hr-agent.yaml` | ⬜ Not yet evaluated | — |

---

## Skill Roster

| Skill | File | Health | Last Evaluated |
|---|---|---|---|
| Principle Alignment | `skills/principle-alignment.yaml` | ⬜ Not yet evaluated | — |
| Spec Consistency Review | `skills/spec-consistency-review.yaml` | ⬜ Not yet evaluated | — |
| Beginner Perspective | `skills/beginner-perspective.yaml` | ⬜ Not yet evaluated | — |
| Implementability Assessment | `skills/implementability-assessment.yaml` | ⬜ Not yet evaluated | — |
| DX Audit | `skills/dx-audit.yaml` | ⬜ Not yet evaluated | — |
| Lateral Thinking | `skills/lateral-thinking.yaml` | ⬜ Not yet evaluated | — |
| Agent Evaluation | `skills/agent-evaluation.yaml` | ⬜ Not yet evaluated | — |
| Agent Design | `skills/agent-design.yaml` | ⬜ Not yet evaluated | — |

---

## Agent Metrics

Each agent has 3–5 observable effectiveness metrics defined below.
Metrics are set by the HR Agent and updated when an agent's responsibilities change.

<!-- Template for each agent section:

### <Agent Name>

**Metrics**:
| # | Metric | 🟢 Threshold | 🟡 Threshold | 🔴 Threshold |
|---|---|---|---|---|
| 1 | <description> | <green condition> | <yellow condition> | <red condition> |

**Evidence Log**:
| Session / Process Run | Metric 1 | Metric 2 | … | Notes |
|---|---|---|---|---|
| <run ID or date> | 🟢/🟡/🔴 | 🟢/🟡/🔴 | … | <observation> |

**Improvement History**:
| Date | Change | Outcome |
|---|---|---|
| <date> | <what was changed> | <result at next evaluation> |

-->

### PM

**Metrics**:
| # | Metric | 🟢 Threshold | 🟡 Threshold | 🔴 Threshold |
|---|---|---|---|---|
| 1 | Sessions end with a documented decision or explicit "defer" | ≥ 90 % of sessions | 70–89 % | < 70 % |
| 2 | Blockers are identified and assigned an owner within the same session | ≥ 90 % of blockers | 70–89 % | < 70 % |

> **Tracking note (metric 2)**: at the end of each session the PM records a
> "Blockers" section in the session notes listing each blocker, the session it
> was raised in, and the session it was assigned an owner. This log is the
> denominator for metric 2 calculations.
| 3 | At least one process improvement is proposed after every 3 sessions | Every 3 sessions | Every 5 sessions | Less frequently |
| 4 | Backlog is re-prioritised when new information arrives | Done same session | Done within 2 sessions | Rarely or never |

**Evidence Log**: _No sessions run yet._

**Improvement History**: _No improvements applied yet._

---

### Architect

**Metrics**:
| # | Metric | 🟢 Threshold | 🟡 Threshold | 🔴 Threshold |
|---|---|---|---|---|
| 1 | Cross-feature conflicts caught before acceptance vs. found post-acceptance | ≥ 80 % caught pre-acceptance | 60–79 % | < 60 % |
| 2 | Every accepted feature has documented design rationale | 100 % | 80–99 % | < 80 % |
| 3 | Principle alignment verdict produced for each feature review | 100 % of reviews | 80–99 % | < 80 % |
| 4 | Proposals to simplify complex feature designs per session | ≥ 1 per session | 1 per 2 sessions | Rarely |

**Evidence Log**: _No sessions run yet._

**Improvement History**: _No improvements applied yet._

---

### Compiler Specialist

**Metrics**:
| # | Metric | 🟢 Threshold | 🟡 Threshold | 🔴 Threshold |
|---|---|---|---|---|
| 1 | Implementability assessment produced for every draft feature | 100 % | 80–99 % | < 80 % |
| 2 | Spec ambiguities identified and flagged per feature review | ≥ 1 per feature | 1 per 3 features | Rarely |
| 3 | Error message proposals included in feature reviews | 100 % of features | 80–99 % | < 80 % |
| 4 | Difficulty classification (Low/Medium/High/Very-High) provided for each feature | 100 % | 80–99 % | < 80 % |

**Evidence Log**: _No sessions run yet._

**Improvement History**: _No improvements applied yet._

---

### Tooling Master

**Metrics**:
| # | Metric | 🟢 Threshold | 🟡 Threshold | 🔴 Threshold |
|---|---|---|---|---|
| 1 | LSP capability list produced for every accepted feature | 100 % | 80–99 % | < 80 % |
| 2 | Formatter ambiguities identified per feature review | ≥ 1 per session | 1 per 3 sessions | Rarely |
| 3 | DX audit completed for each milestone | Every milestone | Every other milestone | Rarely |

**Evidence Log**: _No sessions run yet._

**Improvement History**: _No improvements applied yet._

---

### New User

**Metrics**:
| # | Metric | 🟢 Threshold | 🟡 Threshold | 🔴 Threshold |
|---|---|---|---|---|
| 1 | Actionable doc-gap findings per review session | ≥ 3 | 1–2 | 0 |
| 2 | Beginner error simulations produced for each feature | 100 % | 80–99 % | < 80 % |
| 3 | Learnability rating provided with justification for every feature | 100 % | 80–99 % | < 80 % |

**Evidence Log**: _No sessions run yet._

**Improvement History**: _No improvements applied yet._

---

### Evangelist

**Metrics**:
| # | Metric | 🟢 Threshold | 🟡 Threshold | 🔴 Threshold |
|---|---|---|---|---|
| 1 | Elevator pitch produced for every accepted feature | 100 % | 80–99 % | < 80 % |
| 2 | Tutorial skeleton produced per major feature | 100 % | 80–99 % | < 80 % |
| 3 | Audience mapping provided for each feature | 100 % | 80–99 % | < 80 % |

**Evidence Log**: _No sessions run yet._

**Improvement History**: _No improvements applied yet._

---

### Chaos Agent

**Metrics**:
| # | Metric | 🟢 Threshold | 🟡 Threshold | 🔴 Threshold |
|---|---|---|---|---|
| 1 | Wild alternatives proposed per brainstorm session | ≥ 3 | 1–2 | 0 |
| 2 | Adversarial examples produced per feature under example generation | ≥ 2 | 1 | 0 |
| 3 | Hidden assumptions identified per feature proposal | ≥ 2 | 1 | 0 |
| 4 | At least one idea per session adopted or scheduled for further exploration | Every session | Every other session | Rarely |

**Evidence Log**: _No sessions run yet._

**Improvement History**: _No improvements applied yet._

---

### Spec Writer

**Metrics**:
| # | Metric | 🟢 Threshold | 🟡 Threshold | 🔴 Threshold |
|---|---|---|---|---|
| 1 | Decisions captured in spec prose within the same session they are made | 100 % | 80–99 % | < 80 % |
| 2 | Open spec items list updated after every session | Every session | Every other session | Rarely |
| 3 | Terminology glossary entries added for every new defined term | 100 % | 80–99 % | < 80 % |
| 4 | At least one normative + one counter-example per spec section | 100 % | 80–99 % | < 80 % |

**Evidence Log**: _No sessions run yet._

**Improvement History**: _No improvements applied yet._

---

### Security Advisor

**Metrics**:
| # | Metric | 🟢 Threshold | 🟡 Threshold | 🔴 Threshold |
|---|---|---|---|---|
| 1 | Vulnerability pattern review produced for every feature | 100 % | 80–99 % | < 80 % |
| 2 | Safe-by-default design alternative proposed whenever a risk is identified | 100 % of risks | 80–99 % | < 80 % |
| 3 | Threat model updated when new capabilities are added | Every relevant feature | Every other relevant feature | Rarely |

**Evidence Log**: _No sessions run yet._

**Improvement History**: _No improvements applied yet._

---

### HR Agent

**Metrics**:
| # | Metric | 🟢 Threshold | 🟡 Threshold | 🔴 Threshold |
|---|---|---|---|---|
| 1 | Full evaluation cycle completed within the target cadence | Every 3–5 runs | Every 6–8 runs | Less frequently |
| 2 | Every 🟡/🔴 finding paired with a concrete improvement proposal | 100 % | 80–99 % | < 80 % |
| 3 | Approved improvements implemented within the same review cycle | 100 % | 80–99 % | < 80 % |
| 4 | Capability gaps detected before they cause a process to stall | ≥ 80 % detected proactively | 60–79 % | < 60 % |

**Evidence Log**: _No evaluations run yet._

**Improvement History**: _No improvements applied yet._

---

## Changelog

| Date | Agent / Skill | Change | Author |
|---|---|---|---|
| — | — | Registry created | HR Agent |
