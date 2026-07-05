---
name: less-stupid-opus-gpt55-with-fable
description: Thin anti-slop pre-router for Claude, Codex, Opus, GPT 5.5, and similar coding agents. Use when a task is ambiguous, multi-step, debugging-heavy, rendered-UI/product-quality oriented, Fable-like but Fable is unavailable, or likely to suffer from agent flailing. Routes once to a specific workflow when one clearly matches, lets small tasks move directly, and uses evidence-based Exit Proof for substantial implementation, debugging, or visual/artifact work.
---

# Less Stupid Opus & GPT 5.5 with Fable

Use this as a thin operator in front of the real work. Keep the agent sharp and
evidence-driven: route fast, keep small tasks light, and bring evidence for big
ones. Keep the skill lightweight and practical.

## First Rule

Match the response to the task size.

- Give one-liners a one-line path.
- Give refactors enough context, verification, and review to be trustworthy.
- Add structure only when it raises accuracy, safety, or usability.

## Routing

Do this first, in order:

1. If a specific skill, workflow, or tool clearly matches, route to it once and
   let that workflow own the work.
2. If the task is small and direct, just do it. Keep the report brief.
3. If the task is multi-step implementation, debugging, rendered UI/media, or
   product-quality work, run the matching loop below and finish with Exit Proof.
4. If the loop has converged and cannot improve with the current path, escalate
   with the evidence that shows why.

## Exit Proof

Use Exit Proof for substantial implementation, debugging, rendered UI/media,
scripts/CLI, generated artifacts, or product-quality work. Keep quick answers,
tiny edits, and pure discussion lightweight.

For a sharper checklist, load `references/exit-proof.md`.

Before claiming done, state or internally verify:

```md
Exit Proof:
- changed files:
- observation:
- visual or artifact evidence, if relevant:
- check:
- remaining risk:
```

Rules:

- `changed files` means actual paths touched.
- `observation` means a command, test, runtime result, or reproduced behavior
  actually seen. Prefer "I ran/observed X" over "this should work."
- `visual or artifact evidence` means screenshot, render, video, PDF/image/file
  output, or sample result when the task is visual or artifact-producing.
- `check` means self-review at minimum; use an independent review for risky,
  broad, security-sensitive, or product-quality work when available.
- `remaining risk` names what was not tested or could still break.

If observation is unavailable, say exactly what was run, what was not run, and
what remains unverified.

## Loops

### Product-Feel Loop

Use when the user says a UI, media artifact, or product experience "feels off",
"looks wrong", "is not smooth", "is too empty", or similar.

1. Translate subjective feedback into observable mechanics: spacing, contrast,
   hierarchy, density, motion timing, interaction states, copy, empty states, or
   visual rhythm.
2. Implement or propose the smallest package that addresses the product gap.
3. Verify rendered output with screenshot, video, render, or generated artifact
   when practical.
4. Treat visual work as complete only after checking the rendered result when
   practical.

### Debugging Loop

Use when the cause is unknown, surprising, flaky, or cross-file.

1. Reproduce or observe the failure first.
2. For non-obvious causes, keep at least two competing hypotheses alive.
3. Gather evidence that confirms or rejects each hypothesis.
4. Trace the causal chain to the source. Fix the source, not just the symptom.
5. Verify before and after with the same observation that showed the bug.

If the root cause is obvious and low-risk, skip the hypothesis ritual and verify
the direct fix.

### Fable-Unavailable Mode

Use when a preferred high-capability model, tool, reviewer, or Fable-like path is
unavailable.

Stay active when a preferred path is unavailable. Transfer the work loop first:

1. Read the direct artifact or source of truth.
2. Explore the problem fully with the model/tools available.
3. Produce concrete options, implementation, or review evidence.
4. Discover real capability limits through evidence, not assumption.

Escalate once evidence shows the loop has converged: repeated failed attempts on
the same cause, flat output after honest exploration, unresolvable conflicting
evidence, or a user-owned decision about scope, taste, risk, or irreversible
action.
