# Process: DX Brainstorm

## Purpose
Dedicated creative sessions to improve the Developer Experience (DX) of the
language holistically—not just feature-by-feature, but across the full journey
from discovery to production use. DX Brainstorm sessions are generative, not
evaluative; wild ideas are welcome and no idea is rejected during the session.

## When to Run
- Once per design milestone
- When user testing reveals systemic DX issues
- When a new target audience is identified
- Proactively, to stay ahead of ergonomics debt

## Participating Agents
| Agent | Role in this process |
|---|---|
| PM | Facilitates; keeps energy high; captures all ideas |
| New User | Anchors ideas to the first-time developer perspective |
| Tooling Master | Grounds ideas in what tooling can realistically deliver |
| Evangelist | Connects ideas to the community and education story |
| Chaos Agent | Generates wild, unexpected DX ideas |
| Architect | Identifies which DX improvements require language changes |
| Security Advisor | Flags DX improvements that could inadvertently reduce security |

## Session Structure

### 1. DX Audit (20 min — New User + Tooling Master)
Before generating new ideas, take stock of the current DX state:
- Walk through the full developer journey: discover → install → hello world →
  build something real → deploy → debug → contribute to a library
- For each stage, rate the experience: 😊 Good / 😐 Neutral / 😞 Painful
- List the top 5 friction points

### 2. Inspiration Round (15 min — All Agents)
Each agent brings one DX idea from outside the language world:
- A UX pattern from a mobile app
- A workflow from a game engine
- An onboarding technique from a SaaS product
- A debugging tool from a different language
No critique during this round. Ideas are listed without judgment.

### 3. Feature-Level DX Review (30 min — Tooling Master + New User)
For each recently accepted feature:
- "What is the best possible IDE experience for this feature?"
- "What would a perfect error message for a common mistake look like?"
- "Could this feature's syntax be made more auto-completable?"
- "Is there a shorthand or sugar form that would make common cases delightful?"

### 4. Wild Ideas Round (15 min — Chaos Agent leads)
The Chaos Agent proposes 5–10 unconventional DX ideas, for example:
- A visual type explorer built into the language itself
- A "why did the compiler reject this?" natural language explanation mode
- A "time-travel debugging" mode for pure functions
- A social code-sharing feature in the REPL
Other agents build on, combine, or invert these ideas freely.

### 5. Idea Triage (15 min — PM)
PM leads the group through the collected ideas and applies labels:
- `quick-win`: low effort, high impact — schedule immediately
- `strategic`: high effort, high impact — plan for a future milestone
- `speculative`: needs more research before deciding
- `out-of-scope`: great idea but not for this language

### 6. Action Items (PM)
PM produces a DX improvement backlog update:
- New items added to the backlog from this session
- Quick-wins assigned to owners with target sessions
- Strategic items added to the roadmap

## Outputs
- Session notes: `docs/dx-brainstorm/YYYY-MM-DD.md`
- Updated DX backlog in the project tracker

## Success Criteria
- At least three actionable ideas emerge from every session
- At least one quick-win is implemented before the next session
- The DX audit score improves over successive sessions
