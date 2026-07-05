# Exit Proof

Use this only for multi-step implementation, debugging, rendered UI/media,
scripts/CLI, generated artifacts, or product-quality work. Small direct tasks
skip it.

The point is simple: stop claiming "done" without looking.

## The Five Lines

1. Changed files
   - List the real paths touched.
   - If you cannot list them, you do not know what changed.

2. Observation
   - Include one command, test, runtime result, or reproduced behavior you
     actually saw.
   - "It should work" is not an observation.

3. Visual or artifact evidence
   - Visual change: screenshot, render, or video.
   - Generated file/report/image/PDF: sample output or rendered artifact.
   - Nothing visual and no artifact: skip this honestly.

4. Check
   - Self-review at minimum.
   - Risky or important work: independent review when available.
   - The author should not be the only judge of high-risk work.

5. Remaining risk
   - Name what was not tested, skipped edge cases, or where it could still break.
   - Naming risk is not failure. Hiding it is.

## Anti-Patterns This Kills

- "Done" with no command run.
- Visual work signed off from a diff without rendering.
- One hypothesis, first guess, symptom patched, source untouched.
- Giving up early because a preferred model or tool was unavailable.
- Dumping a full transcript instead of summarizing the pattern.
