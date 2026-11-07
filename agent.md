# HiMCM four-person agent workflow

Repository: https://github.com/YeeJiangBIGZ/18105. Updated 2026-11-07. These rules coordinate the four human teammates and their agents; agents do not acquire authority to make team decisions or contact teammates merely by reading this file.

## Start every work session

1. Read this file, README's current decisions and task table, then the relevant design/research sections. Check the original Problem B when interpreting a requirement. Do not assume this lowercase filename is automatically loaded by every agent application.
2. Inspect `git status --short --branch`, fetch origin and inspect new commits. Work on **main only**; create no branches. With a clean working tree, update using `git pull --ff-only origin main`. If local commits or edits prevent that, inspect and reconcile them; do not reset, clean, overwrite or automatically stash another person's work.
3. Identify the requesting human and the concrete task. Honor any narrower scope in their request. Current shared scope is planning, decisions and research; manuscript edits and implementation need an explicit human task expanding that scope. Ordinary authorized work and synchronization do not need repeated permission.
4. Check the README task table. Before editing a shared section, claim a bounded task there with your human/agent identifier, exact file/heading, starting main SHA and next deliverable. Push that small claim, then fetch and verify it survived integration. This is a coordination record, not an atomic lock.

## Four work lanes

These divide responsibilities, not named people. Teammates claim lanes/tasks according to their actual agreement; a person may rotate roles. Do not invent assignments or claim another member approved something.

| Lane | Main responsibility | Handoff |
|---|---|---|
| Coordination/integration | Original requirements, task ownership, interfaces, accepted decisions and final consistency | README status and a bounded next task |
| Physical model | Cooler/outlet inputs; airflow, temperature and moisture; boundary conditions and physical checks | Design component with units, assumptions and output contract |
| People and optimization | Paths/dwell time, comfort versus safety, aggregation, objectives/constraints and candidate screening | Design component linked to physical outputs and required evidence |
| Research and verification | Primary sources, parameter suitability, limitations, independent checks and sensitivity | Research evidence plus a specific verification finding linked to the design |

Any different teammate/agent can check a component; verification is not restricted to one lane. Different agents agreeing is not evidence of correctness. Recheck sources, equations, units or reproducible results independently.

## Ownership and coordination

- Edit only claimed sections and necessary linked records. Different non-overlapping sections can proceed concurrently. Avoid document-wide formatting while another person edits that file. Shared notation/interfaces or README decisions belong to a separately scoped integration task.
- If a section is claimed, continue unrelated research/read-only analysis, or ask the requesting human to coordinate the handoff. Do not overwrite a claim or assume it expired merely because it is old. On the same machine, also preserve unrelated working-tree and staged edits.
- Keep task states `claimed`, `working`, `ready for review`, `blocked`, or `done`. A blocker names what is missing and the next action. A task is done when its stated deliverable is checked and published; this does not automatically accept its scientific proposal.
- When publishing a result, record its section link, key change, checks, unresolved issues and next owner/action in the task row. Use a different reviewer where feasible for consequential equations or empirical claims. Unreviewed proposals may be committed but must stay labeled unreviewed.
- Separate **decision state** (`proposed`, `accepted`, `superseded`) from **verification state** (`unchecked`, `checked with stated scope`, `failed`). Only explicit human decisions can promote a substantive assumption/weight/model choice to accepted; record who decided and when. Existing authorization remains valid—do not ask again for routine edits.

## Model complexity and paper length

Owner instruction, 2026-11-07: explore accuracy now, but keep the model mathematically simple and explainable. If the 25-page submission limit becomes binding, simplify the model and remove nonessential extensions while retaining required outputs. Discussion does not make every feature mandatory. Separate the core from optional extensions in design.md; do not silently drop consequential effects or label untested assumptions accurate. No particular feature or page allocation is fixed yet.

Owner clarification, 2026-11-07: aim for convex continuous structure even with mixed-integer installation choices. Do not force it with piecewise-linear segmentation or an artificial personal wind-direction preference. Stronger assumptions need explicit justification; distinguish spatial candidate refinement from utility approximation. Convex excessive-wind penalties do not by themselves represent useful fan cooling.

## File ownership and evidence

- `README.md`: project entry point, requirements, task table, accepted decisions, blockers and next action.
- `design.md`: component definitions, equations, units, assumptions, interfaces, optimization and verification plans/results. Follow its contribution workflow.
- `research.md`: sourced findings, parameter candidates, applicability and contradictions. Follow its evidence workflow. A sourced claim does not automatically become an adopted model input.
- `agent.md`: shared workflow rules. Change when a human requests a workflow change; keep decisions and technical content in their own files.

Keep these four Markdown records consolidated. Other necessary project artifacts are allowed; avoid parallel diaries or competing specifications. `package-info.md` is local-only and Git-ignored. Never commit credentials, temporary captures or generated build output. Preserve actual AI assistance and source access limitations for disclosure.

## Publish safely on main

1. Review the diff and stage only your task's files/hunks. Do not use blanket staging when unrelated work exists. Check links, units, scope and the verification appropriate to the change; no gratuitous tests for documentation-only edits.
2. Commit a small coherent change identifying the affected component or evidence. Fetch again and inspect new remote changes.
3. If origin/main advanced, integrate it before pushing. Rebase only your own unpublished commits when safe; otherwise merge without discarding either contribution. For conflicts, compare both versions and their meaning, not just Git markers. If the same design choice conflicts, preserve the alternatives as proposed and refer the unresolved decision to the human team. Rerun affected checks.
4. Push main normally. If rejected because another teammate pushed, fetch, inspect, integrate and retry. **Never force-push main or rewrite published teammate history.** A claim is effective only after remote verification; a rejected claim must be reconciled before editing its section.
5. Verify the pushed commit is present on remote main, read back the changed files at that commit, and report the commit/link and any remaining gaps. A later teammate commit may become the tip; check ancestry rather than insist your commit remain HEAD. GitHub publication and Overleaf synchronization are separate outcomes.

No PR/branch workflow is required. Do not send external messages, change repository access or publish the private project without an explicit task authorizing that action.
