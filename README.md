# Less Stupid Opus & GPT 5.5 with Fable

A lightweight anti-slop operator skill for coding agents.

The joke is on the agent, not the user: agents flail. They over-process tiny
tasks, improvise through risky ones, claim "done" without looking, and sometimes get weirdly
pessimistic when a preferred model or tool is unavailable.

This skill is a thin pre-router that helps an agent flail less:

- route once when a specific workflow clearly matches;
- keep small direct tasks lightweight;
- define what done looks like before substantial work starts;
- require real evidence for multi-step implementation, debugging, rendered UI,
  and product-quality work.

It is deliberately small and practical.

## What It Does

`less-stupid-opus-gpt55-with-fable` gives an agent a compact operating loop:

| Situation | Behavior |
| --- | --- |
| A specific skill or workflow clearly matches | Route once, then get out of the way |
| The task is small and direct | Just do it; keep the report brief |
| The task is multi-step, risky, visual, or executable | Define done, then finish with Exit Proof |
| A preferred model/path is unavailable | Transfer the work loop first; discover limits through evidence |
| The current loop stops improving | Escalate with evidence |

Exit Proof means:

- observable done condition;
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

Most of the time, it should act as a quiet front door. The user does not need to
mention Fable; the work shape is enough:

- For tiny tasks, it should stay lightweight.
- For weird bugs, it should reproduce or observe before fixing.
- For visual/product-feel tasks, it should translate taste into mechanics and
  verify the rendered result.
- For multi-step work, it should finish with evidence.

## Customize

Keep customization lean:

- Add your preferred test command to the Exit Proof wording.
- Map "independent review" to your own reviewer, teammate, or second agent.
- Add stack-specific visual evidence, such as browser screenshots, simulator
  captures, generated image snapshots, or PDF renders.
- Keep only the sections you actually use.

The value is lighter motion with better evidence.

## License

MIT. See [LICENSE](LICENSE).
