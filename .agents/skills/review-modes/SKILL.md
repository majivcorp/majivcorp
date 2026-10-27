---
name: review-modes
description: Opt-in coding and code-review modes for RebirthCo and Majivu. Use when explicitly asked for Ponytail (off/lite/full/ultra), PStack/poteto-mode, thermonuclear code-quality review, Thermos, or an independent EGM specification review. Do not auto-enable plugins, alter CI, or override existing repository safety controls.
---

# Optional engineering review modes

Default: OFF. These are opt-in **workflows**, not permission to make unreviewed changes.

## Toggles

- `Ponytail lite|full|ultra`: choose the smallest correct complete change, reuse existing code, preserve tests/security/accessibility and explain what was omitted. `Ponytail off`: disable.
- `PStack on`: use the installed upstream `poteto-mode` router for scoped planning, design, implementation and verification. `PStack off`: disable routing. If not installed, do not pretend it ran.
- `Thermo review`: use PStack's `thermo-nuclear-code-quality-review` skill for a strict maintainability, architecture, indirection, branching, and type/boundary review.
- `Thermos`: use the PStack combined independent code-quality + correctness/security review if available. Do not invent a second reviewer if unavailable.
- `EGM`: review a frozen specification with separated planner and skeptical reviewers; compare findings to code, policy, and tests. Treat AI reviewer findings as hypotheses, not proof.

## Workflow

1. Read `AGENTS.md`, relevant established ADRs and current code/test patterns. Lock review to exact base and head SHAs if reviewing a PR.
2. Run available deterministic checks before model-based critiques. Record what actually ran.
3. Apply only requested optional modes and deduplicate reviewer findings.
4. For each finding state severity, exact location, supporting evidence, effect, and smallest justified correction.
5. Do not automatically rewrite code from a review. Keep all changes scoped, testable, reversible, and in a reviewable branch.
6. Never relax security, access controls, tenancy, audit, financial integrity, clinical-safety controls, or applicable legal requirements. A founder-approved design override still requires relevant implementation and release gates.

## Sources, licensing and installation

- Ponytail: https://github.com/DietrichGebert/ponytail (MIT). Supports lite/full/ultra/off. Default off should be configured in the upstream host; this file alone does not persist the switch.
- PStack port: https://github.com/michael-denyer/pstack-claude (MIT and upstream notices). Includes `poteto-mode`, `thermo-nuclear-code-quality-review`, `thermo-nuclear-review` and `thermos`. Install via the upstream documented plugin marketplace for the actual host, only after reviewing repository hooks and permissions.
- Google EGM: https://github.com/google/elephant-goldfish-model. Use as a review pattern unless its plugin is separately installed and verified.

Never copy PHI, secrets, or unlicensed research data into plugin prompts. Third-party plugins remain optional, not installed by simply including this skill.
