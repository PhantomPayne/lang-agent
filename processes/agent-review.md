# Process: Agent Review

## Purpose
Systematically evaluate the health and effectiveness of every agent and skill
in the team. Produce concrete improvement proposals for underperformers and,
where a persistent capability gap is identified, design and introduce a new agent.

This is the HR Agent's primary operating process. It runs independently of the
language design processes — it is a *meta-process* about the team itself.

## When to Run
- **Routine**: after every 5 process runs by default (triggered by the PM's
  progress log). Run after 3 process runs instead if any agent is currently
  AT RISK or CRITICAL.
- **Triggered**: immediately when any agent receives two consecutive 🔴 scores
- **Triggered**: when a process stalls because no agent owns the required capability
- **Triggered**: when the PM or any agent requests a team health check

## Participating Agents
| Agent | Role in this process |
|---|---|
| HR Agent | Leads the entire review; owns all outputs |
| PM | Provides session logs and process run history; reviews HR proposals |
| Architect | Reviews any proposed new agent for consistency with team structure |

All other agents are *subjects* of the review, not active participants.

---

## Steps

### Phase 1 — Evidence Collection

#### 1.1 Session Log Harvest (HR Agent)
Collect the outputs from all process runs since the last review:
- Decisions made and which agent drove them
- Issues filed and who identified them
- Spec changes made and who authored them
- Blockers or stalls and which agent was responsible for resolving them

Record findings in `docs/agent-registry.md` under each agent's evidence log.

#### 1.2 Skill Output Audit (HR Agent)
For each skill used in the reviewed sessions, collect:
- Was the skill invoked as specified by its `used_by` list?
- Did the output match the skill's `output_format`?
- Was the output actually used by the next step in the process, or discarded?

---

### Phase 2 — Agent Evaluation

#### 2.1 Individual Agent Evaluations (HR Agent)
For each agent, apply the `agent-evaluation` skill:
- Score against all defined metrics (🟢 / 🟡 / 🔴)
- Identify root causes for any non-green score
- Produce an improvement proposal for each 🟡 or 🔴

#### 2.2 Skill Evaluations (HR Agent)
For each skill, apply the `agent-evaluation` skill in skill mode:
- Evaluate actionability of output format
- Evaluate precision of step list
- Identify any steps that are consistently skipped or produce no usable output

#### 2.3 Overall Team Health Summary (HR Agent)
Produce a one-page team health dashboard:
- Each agent listed with their overall score (HEALTHY / AT RISK / CRITICAL)
- Each skill listed with its overall score
- Top 3 priority actions for the team

---

### Phase 3 — Improvement Cycle

#### 3.1 Proposal Review (PM + Architect)
The PM and Architect review all improvement proposals from Phase 2:
- For **agent system prompt edits**: Architect checks for unintended side effects
  on other processes; PM checks the change doesn't duplicate another agent's role
- For **skill step/format edits**: PM checks the change is backward-compatible
  with existing processes that use the skill

#### 3.2 Adoption (HR Agent)
For each approved proposal:
- Apply the edit to the relevant agent YAML or skill YAML
- Update the agent's metrics in `docs/agent-registry.md`
- Note the change and rationale in the registry's changelog section

#### 3.3 Rejection Handling (HR Agent)
For proposals not adopted:
- Record the rejection reason in `docs/agent-registry.md`
- Identify an alternative improvement approach for the next cycle

---

### Phase 4 — Gap Detection and New Agent Design

#### 4.1 Gap Identification (HR Agent)
After all existing agent evaluations are complete, ask:
- Is there a recurring failure mode or bottleneck that no current agent is
  accountable for solving?
- Is any existing agent's scope so broad that their core responsibilities suffer?
- Has a new process been introduced since the last review that requires expertise
  no current agent has?

If yes to any question, proceed to 4.2. If no, skip to Phase 5.

#### 4.2 Gap Articulation (HR Agent)
Write a one-paragraph description of the capability gap:
- What specific problems occur because this capability is absent?
- What evidence from the session logs supports this?
- Why is improving an existing agent insufficient?

#### 4.3 New Agent Design (HR Agent)
Apply the `agent-design` skill to produce a draft agent YAML:
- Complete system prompt with numbered responsibilities
- Skills list (flagging any new skills that must be created)
- Triggers calibrated to avoid duplicate invocations with existing agents
- Success criteria for the next evaluation cycle

#### 4.4 New Agent Review (PM + Architect)
The PM reviews the draft for process integration.
The Architect reviews for structural consistency with the existing roster.
Both must approve before the agent is adopted.

#### 4.5 New Agent Adoption (HR Agent)
- Commit the new agent YAML to `agents/`
- If new skills are required, create stub skill YAMLs and file them as tasks
- Add the agent to `docs/agent-registry.md` with initial metrics
- Update `README.md` agent table

---

### Phase 5 — Report

#### 5.1 HR Review Report (HR Agent)
Produce a concise review report and store it in `docs/hr-reviews/YYYY-MM-DD.md`:

```
## HR Review — <date>

### Team Health Dashboard
| Agent | Health | Top issue |
|---|---|---|
| <name> | HEALTHY / AT RISK / CRITICAL | <one line> |
...

### Improvements Adopted
- <agent/skill>: <change summary>
...

### Improvements Deferred
- <agent/skill>: <reason>
...

### New Agents Introduced
- <agent name>: <one-line purpose>
...

### Next Review Trigger
<date or event>
```

---

## Outputs
- Updated `docs/agent-registry.md` (scores, evidence, metrics)
- Updated agent and skill YAML files (for approved improvements)
- New agent YAML files (for newly designed agents)
- HR Review Report in `docs/hr-reviews/YYYY-MM-DD.md`

## Success Criteria
- Every agent has at least 3 defined, observable metrics in the registry
- No agent remains at CRITICAL health for more than two consecutive review cycles
- Every approved improvement is implemented within the same review cycle
- Any newly introduced agent has its first evaluation within 5 process runs
