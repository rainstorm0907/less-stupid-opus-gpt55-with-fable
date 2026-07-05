# Less Stupid Opus & GPT 5.5 with Fable

A lightweight anti-slop operator skill for coding agents.

The joke is on the agent, not the user: agents flail. They over-process tiny
tasks, wing risky ones, claim "done" without looking, and sometimes get weirdly
pessimistic when a preferred model or tool is unavailable.

This skill is a thin pre-router that helps an agent flail less:

- route once when a specific workflow clearly matches;
- skip ceremony for small direct tasks;
- require real evidence for multi-step implementation, debugging, rendered UI,
  and product-quality work.

It is deliberately small. It is not a process religion.

## What It Does

`less-stupid-opus-gpt55-with-fable` gives an agent a compact operating loop:

| Situation | Behavior |
| --- | --- |
| A specific skill or workflow clearly matches | Route once, then get out of the way |
| The task is small and direct | Just do it; no checklist |
| The task is multi-step, risky, visual, or executable | Finish with Exit Proof |
| A preferred model/path is unavailable | Transfer the work loop first; discover limits through evidence |
| The current loop stops improving | Escalate with evidence |

Exit Proof means:

- changed files;
- command, test, or runtime observation actually seen;
- screenshot, render, video, or output sample when relevant;
- self-check or independent review for risky work;
- remaining risk.

## Install

Copy the skill folder into your agent's skills directory:

```text
your-skills-dir/
  less-stupid-opus-gpt55-with-fable/
    SKILL.md
    agents/
      openai.yaml
    references/
      exit-proof.md
```

For Codex-style skill folders, the required file is:

```text
less-stupid-opus-gpt55-with-fable/SKILL.md
```

For OpenAI/Codex UI metadata, keep:

```text
less-stupid-opus-gpt55-with-fable/agents/openai.yaml
```

## Use

You can invoke it explicitly:

```text
Use $less-stupid-opus-gpt55-with-fable for this ambiguous implementation task.
```

Most of the time, it should act as a quiet front door:

- For tiny tasks, it should not add ceremony.
- For weird bugs, it should reproduce or observe before fixing.
- For visual/product-feel tasks, it should translate taste into mechanics and
  verify the rendered result.
- For multi-step work, it should not claim completion without evidence.

## Customize

Keep customization lean:

- Add your preferred test command to the Exit Proof wording.
- Map "independent review" to your own reviewer, teammate, or second agent.
- Add stack-specific visual evidence, such as browser screenshots, simulator
  captures, generated image snapshots, or PDF renders.
- Delete sections you will not actually use.

The value is less ceremony, not more.

## Fableize / Qwable Safety Note

This skill borrows only procedure-level ideas from public Fableize, fablize,
Qwable, and similar agent-workflow discussions: verify real outputs, debug from
evidence, and escalate only when the loop stops improving.

It does not include or import leaked prompts, raw chain-of-thought, trace
corpora, distillation datasets, model weights, or persona prompts. Learn the
shape of good work, not private internals.

## License

MIT. See [LICENSE](LICENSE).
