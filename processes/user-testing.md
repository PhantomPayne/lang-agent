# Process: User Testing

## Purpose
Simulate how real developers interact with language features, documentation,
and tooling by having agents roleplay as representative users. This surfaces
usability issues before any real users encounter them.

## When to Run
- After a feature reaches `draft` status and has examples
- After a documentation draft is written
- Before any feature is moved to `accepted`

## Participating Agents
| Agent | Role in this process |
|---|---|
| PM | Designs test scenarios; observes and records; produces the test report |
| New User | Primary test persona: developer learning the language for the first time |
| Evangelist | Secondary test persona: developer converting from a specific other language |
| Chaos Agent | Adversarial test persona: developer trying to misuse or abuse the feature |
| Architect | Observer: identifies spec failures revealed by testing |
| Compiler Specialist | Observer: notes whether error messages adequately guide users |

## User Personas

### Persona A — "The Newcomer" (played by New User)
- Solid experience in one mainstream language (e.g. Python, TypeScript, or Go)
- No prior exposure to this language
- Learns by reading documentation and trying things in a REPL
- Primary goal: build something small and useful in an afternoon

### Persona B — "The Convert" (played by Evangelist)
- Expert in a language similar to this one (e.g. Rust, Haskell, or Kotlin)
- Converting because they've heard good things
- Likely to compare every feature to their home language
- Primary goal: understand what this language does differently and why

### Persona C — "The Abuser" (played by Chaos Agent)
- Experienced developer who enjoys finding edge cases
- Will use every feature in unintended ways
- Primary goal: find surprising or broken behaviour

## Steps

### 1. Scenario Design (PM)
PM designs 3–5 concrete coding tasks for each feature under test. Tasks should:
- Be achievable using only features that are `draft` or `accepted`
- Have a clear success criterion (program produces correct output)
- Vary in difficulty: one trivial, one moderate, one challenging

### 2. Independent Task Attempts (Persona agents — parallel)
Each persona agent attempts each task independently:
- They read only documentation, examples, and the REPL
- They do NOT look at the spec directly (users don't read specs)
- They record every point of confusion, every error message encountered, and
  every time they had to guess what to do

### 3. Debrief (PM facilitates — all agents)
After each task:
- Each persona shares their experience: what worked, what didn't, what surprised them
- Observer agents note spec gaps or misleading error messages that were revealed
- All findings are recorded in the test report

### 4. Findings Classification (PM)
Each finding is classified:
- **UX Bug**: something that behaved differently than documented
- **Doc Gap**: documentation that is missing or unclear
- **Design Issue**: the feature itself needs to be redesigned
- **Error Message Issue**: the compiler's error message was unhelpful
- **Tooling Gap**: the IDE/REPL experience was lacking

### 5. Remediation (PM assigns owners)
- UX Bugs → Architect + Compiler Specialist
- Doc Gaps → Spec Writer + Evangelist
- Design Issues → Architect (may trigger a new design session)
- Error Message Issues → Compiler Specialist
- Tooling Gaps → Tooling Master

### 6. Re-test (PM)
After remediation, PM selects the most critical scenarios and runs them again
with fresh persona agents. Repeat until no new Design Issues or UX Bugs are found.

## Outputs
- User testing report for each feature (`docs/testing/feature-name.md`)
- New issues for all Design Issues and UX Bugs
- Updated documentation and error messages

## Success Criteria
- Persona A can complete the trivial task without consulting anyone
- Persona B correctly predicts language behaviour in at least 70% of cases
- No Design Issues are discovered in re-test
- All error messages adequately guide the user toward a fix
