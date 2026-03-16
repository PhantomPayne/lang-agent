# Core Principles

> **Status**: Three candidate versions generated for comparison.
> Each version was produced by running the full [Core Principles process](../processes/core-principles.md)
> (all 7 steps, all 6 participating agents) with a different thematic emphasis.

## Generated Versions

The team ran the Core Principles process three times, each with a distinct
philosophical lens, to explore the design space before committing to a final set.

| Version | Emphasis | Tagline | Principles | Link |
|---------|----------|---------|------------|------|
| **A** | Safety-First | "If it compiles, it's correct — and you didn't need a PhD to write it." | 7 | [core-principles-v1.md](core-principles-v1.md) |
| **B** | Ergonomics-First | "Simple to start, powerful to stay." | 7 | [core-principles-v2.md](core-principles-v2.md) |
| **C** | Innovation-First | "The language that refuses to limit what you can express." | 7 | [core-principles-v3.md](core-principles-v3.md) |

## Comparison at a Glance

### Version A — Safety-First
1. Safe by Default
2. Errors Are Values, Not Surprises
3. Invalid States Are Unrepresentable
4. Catch Bugs at Compile Time
5. Progressive Disclosure of Complexity
6. Clarity at the Call Site
7. Predictable Performance Cost

### Version B — Ergonomics-First
1. Readable at a Glance
2. One Obvious Path
3. Errors That Teach
4. Progressive Disclosure
5. Tooling Is the Language
6. Explicit Defaults, Implicit Escape Hatches
7. Fast from Edit to Answer

### Version C — Innovation-First
1. The Program Is the Programmable
2. Compile-Time Is the First Runtime
3. Types Serve Expression, Not Bureaucracy
4. Paradigms Are Tools, Not Religions
5. Orthogonal by Design
6. Power Must Be Legible
7. Complexity Is Earned, Not Inherited

## Common Themes

Several ideas appear across all three versions, despite different emphases:

- **Progressive complexity**: All versions commit to keeping simple things simple
  (V-A §5, V-B §4, V-C §7).
- **Compile-time guarantees**: All versions leverage the compiler as a safety net
  (V-A §4, V-B §6, V-C §2).
- **Readable code**: Readability is a first-class concern across all three
  (V-A §6, V-B §1, V-C §6).
- **Explicit error handling**: All versions reject exception-based control flow
  (V-A §2, V-B §3, V-C §3).

## Key Differentiators

| Dimension | Version A | Version B | Version C |
|-----------|-----------|-----------|-----------|
| **Primary value** | Correctness | Productivity | Expressiveness |
| **Target developer** | Systems / safety-critical | Application / general-purpose | Language enthusiasts / power users |
| **Error philosophy** | Errors as values (Result types) | Errors as teaching moments (rich diagnostics) | Errors as type-system feedback |
| **Metaprogramming** | Minimal, gated by `unsafe` | Not a priority | Core design pillar (AST as data) |
| **Performance model** | Predictable, zero-cost abstractions | Fast compilation, acceptable runtime | Compile-time evaluation replaces runtime cost |
| **Tooling** | Standard, ships with compiler | First-class deliverable, unified | Extensible compiler as a platform |

## Next Steps

1. Review all three versions and discuss which principles resonate most strongly
2. Consider a hybrid set that draws the best ideas from each version
3. Run a consensus vote across all agents on the final combined set
4. Commit the final version to this document

---

*Last updated: 2026-03-16*
*Consensus reached: Pending — three candidate versions under review*
