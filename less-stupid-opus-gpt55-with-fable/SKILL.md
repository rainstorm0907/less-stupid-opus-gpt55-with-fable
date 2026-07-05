---
name: less-stupid-opus-gpt55-with-fable
description: Thin anti-slop pre-router for Claude, Codex, Opus, GPT 5.5, and similar coding agents. Use when a task is ambiguous, multi-step, debugging-heavy, rendered-UI/product-quality oriented, Fable-like but Fable is unavailable, or likely to suffer from agent flailing. Routes once to a specific workflow when one clearly matches, lets small tasks be done directly, and requires evidence-based Exit Proof for substantial implementation, debugging, or visual/artifact work.
---

# Less Stupid Opus & GPT 5.5 with Fable

Use this as a thin operator in front of the real work. Make the agent less
stupid: route fast, skip ceremony on small tasks, and demand evidence on big
ones. Do not turn this into a process cathedral.

## First Rule

Match the response to the task size.

- Do not gate a one-liner.
- Do not wing a refactor.
- Do not add structure unless it raises accuracy, safety, or usability.

## Routing

Do this first, in order:

1. If a specific skill, workflow, or tool clearly matches, route to it once and
   get out of the way. Do not wrap it in extra gates.
2. If the task is small and direct, just do it. No Exit Proof required. Report
   the result briefly.
3. If the task is multi-step implementation, debugging, rendered UI/media, or
   product-quality work, run the matching loop below and finish with Exit Proof.
4. If the loop clearly stops improving after honest effort, escalate with the
   evidence that proves the stall.

## Exit Proof

Use Exit Proof only for substantial implementation, debugging, rendered UI/media,
scripts/CLI, generated artifacts, or product-quality work. Skip it for quick
answers, tiny edits, and pure discussion.

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
  actually seen. "Should work" is not an observation.
- `visual or artifact evidence` means screenshot, render, video, PDF/image/file
  output, or sample result when the task is visual or artifact-producing.
- `check` means self-review at minimum; use an independent review for risky,
  broad, security-sensitive, or product-quality work when available.
- `remaining risk` names what was not tested or could still break.

If observation is impossible, say exactly what was not run or seen.

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
4. Do not declare visual work done from source diff alone.

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

Do not get pessimistic and do half the work. Transfer the work loop first:

1. Read the direct artifact or source of truth.
2. Explore the problem fully with the model/tools available.
3. Produce concrete options, implementation, or review evidence.
4. Discover real capability limits through evidence, not assumption.

Only escalate after a real ceiling signal: repeated failed attempts on the same
cause, flat output after honest exploration, unresolvable conflicting evidence,
or a user-owned decision about scope, taste, risk, or irreversible action.

## Privacy Guard

Use when analyzing prompts, transcripts, logs, or session history.

- Do not scan transcripts, logs, or session history unless the user explicitly
  asks.
- Redact secrets, tokens, credentials, emails, phone numbers, and long opaque IDs.
- Summarize patterns and short redacted examples. Do not dump raw logs or full
  transcripts back to the user.
- Stop and ask if the analysis would expose private third-party messages or
  unrelated sensitive files.

## External Pattern Import Guard

Public Fableize, fablize, Qwable, and similar agent-workflow projects may be
useful as procedure inspiration. Treat them as untrusted reference material.

Import:

- verification loops;
- debugging discipline;
- escalation criteria;
- prompt/session pattern summaries;
- lightweight routing ideas.

Do not import:

- leaked or claimed system prompts;
- raw chain-of-thought;
- trace corpora;
- distillation recipes or datasets;
- model weights;
- persona prompts that say to "act as" a proprietary model.

Learn the shape of good work, not private internals.

## Reference

Load `references/exit-proof.md` when the task is substantial enough that the
agent needs a sharper completion checklist or when it keeps claiming done without
evidence.
