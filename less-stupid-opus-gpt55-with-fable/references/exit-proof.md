# Exit Proof

Use this only for multi-step implementation, debugging, rendered UI/media,
scripts/CLI, generated artifacts, or product-quality work. Small direct tasks
can stay lightweight.

The point is simple: look at the work before calling it done.

## The Five Lines

1. Changed files
   - List the real paths touched.
   - Clear paths make the scope reviewable.

2. Observation
   - Include one command, test, runtime result, or reproduced behavior you
     actually saw.
   - Prefer "I ran/observed X" over "this should work."

3. Visual or artifact evidence
   - Visual change: screenshot, render, or video.
   - Generated file/report/image/PDF: sample output or rendered artifact.
   - When nothing visual or artifact-producing changed, say that plainly.

4. Check
   - Self-review at minimum.
   - Risky or important work: independent review when available.
   - High-risk work benefits from a second judge.

5. Remaining risk
   - Name what was not tested, skipped edge cases, or where it could still break.
   - Naming risk makes the handoff stronger.

## Patterns This Encourages

- Completion grounded in an observed command, runtime check, or artifact.
- Visual work checked in the rendered surface.
- Debugging from cause, not just symptom.
- Active exploration even when a preferred model or tool is unavailable.
- Concise evidence instead of bulky raw output.
