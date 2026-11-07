# HiMCM 2026 — Team 18105

Problem B: **Air Conditioning the Environment: Modeling Energy Waste in Public Cooling**. Updated 2026-11-07.

## Workspace and records

All collaboration uses the **main branch** of [YeeJiangBIGZ/18105](https://github.com/YeeJiangBIGZ/18105), synchronized with the local HiMCM workspace. Do not create separate branches. Current work is planning, decisions and research; this does not authorize changing the manuscript or implementing the model yet.

- [agent.md](agent.md): agent workflow, synchronization and collaboration rules.
- [README.md](README.md): agreed scope, current decisions, requirements and next action.
- [design.md](design.md): equations, candidate objectives, configuration choices and unresolved modeling assumptions.
- [research.md](research.md): source evidence, venue precedents and limitations.
- [Original problem](2026_HiMCM_Problem_B.pdf): authoritative requirements.
- [main.tex](main.tex): teammate's manuscript; currently the initial Overleaf skeleton.

Keep these four Markdown records consolidated. Other project artifacts such as the PDF, manuscript, data or code may exist when needed; this is not a four-file cap. `package-info.md` is a local-only, Git-ignored inventory. Record agreed decisions on GitHub as well as locally, and check teammate changes before editing. GitHub delivery alone does not establish Overleaf synchronization.

## Team startup and task table

Each of the four teammates should give their agent this startup instruction:

> Read agent.md and README.md, fetch current main, then read the relevant design.md and research.md sections. Follow the shared task-claim and synchronization workflow. Work only on main, preserve teammate work, and distinguish proposed assumptions from accepted decisions. My task for you is: [specific task].

Use the four lanes in [agent.md](agent.md#four-work-lanes); no personal assignments have been made here. The table records active work and pending handoffs, not a transcript. Keep completed rows only while they are useful, then fold their durable outcomes into the relevant document. An agent's unverified proposal is not an accepted team decision.

| Task | Human / agent | File and section | Starting main SHA | State | Deliverable / checks / handoff |
|---|---|---|---|---|---|
| Record small-case enumeration and body blockage | John / general-chat agent | README decisions; design.md people and screening | 8f223c3 | claimed | Record exhaustive small-case benchmarks and approximate larger-case search; simple-body treatment, with physical accuracy distinguished from search coverage. |

Next technical tasks remain unclaimed: define bus-shelter geometry/scenarios; choose airflow and temperature interfaces; define occupant exposure/benefit; verify candidate inputs and the screening approximation. Teammates should claim concrete sections before starting those edits.

## Agreed scope and decisions

Start with a simple **open-sided bus shelter**, comparing the required fan and two evaporative coolers. Enclosure changes are set aside for now. Shade is not explicitly named as a system in the problem, although facility design and solar exposure are; holding the shelter's shade fixed is a proposed comparison condition. No specific cooler or outlet arrangement has been selected.

Use four categories: **benefit to people, all financial costs, environmental effects, and nonfinancial practicality**. Reliability affects each rather than receiving a separate score. Comfort can improve toward an optimum and worsen with overcooling; health protection is distinct and needs its own justified measure. Final metrics, weights, comfort functions and safety thresholds remain undecided.

**Complexity rule — John, 2026-11-07:** explore accuracy now, then simplify and remove nonessential extensions if needed to fit the 25-page paper. Favor mathematical elegance, clear explanation and required results over accumulating mechanisms. No particular feature has been selected for removal. See [design reduction rule](design.md#complexity-and-the-25-page-paper).

**Wind/convexity clarification — John, 2026-11-07:** retain convex continuous structure with binary installation choices as needed; do not impose a preferred wind direction or use segmentation merely to force convexity. John proposed an excessive-speed ceiling with no penalty below it. The convex ceiling penalty is recorded; its threshold and positive fan-cooling benefit remain unresolved. This does not cancel spatial candidate refinement. See [wind formulation](design.md#convexity-and-direction-independent-wind-penalty).

The general chat coordinates the work; verification/ideas may use separate chats. Explain models before code, verify one complete small case before scaling, and preserve actual AI-assistance provenance.

## Required outputs from the source

1. Use an open freezer case to justify what cooling efficiency should measure.
2. Develop an efficiency measure for an open bus shelter comparing fan, evaporative cooler and large evaporative cooler.
3. Revise it for a semi-open rail-station waiting area and explain what changed and why.
4. Apply it to at least two specific venues differing in climate or cooling system; assess scaling and drivers of efficiency. Real data or justified estimates are allowed.
5. Extend the analysis to balance performance, visitor experience, energy and cost.
6. Recommend operating strategies including during extreme heat; produce a 1–2 page COO memo for one venue and a public blog post.
7. PDF of at most 25 pages including summary sheet, contents, solution, memo and references. The required AI-use report, if applicable, is excluded from that limit. Include the required blog even though it is omitted from the final PDF checklist.

## Source details and unresolved interpretation

- Fan: makes the space feel up to 3°C cooler; listed energy use 0.25 kW/hr.
- Evaporative cooler: lowers air temperature up to 5°C; 1.2 kW/hr.
- Large evaporative cooler: lowers air temperature up to 8°C; 2.5 kW/hr.
- Perceived and air-temperature reductions are different quantities. The stated maxima are not established performance under every condition.
- The source's kW/hr label is dimensionally ambiguous. Interpreting the figures as average kW is a possible assumption, not a confirmed correction.

## Current working model

Discussed structure, not a validated implementation:

1. Describe coolers and outlets by technology, capacity, position, direction, area and flow; shared outlets remain subject to equipment limits.
2. Predict local airflow, temperature and humidity for the configuration, weather and venue geometry. A side-mounted outlet was an example, not a chosen installation.
3. Represent occupants as points with arrival/departure times and paths. Constant-position paths represent stationary occupants. Integrate benefit over exposure time; distance integrals require inverse-speed weighting and separate waiting contributions.
4. John supports sampling occupancy moments/segments and averaging. The proposed time-snapshot method computes benefit first and duration-weights it; sampling and steady-state validity remain open. See [walking flow and snapshots](design.md#walking-flow-and-snapshot-averaging).
5. Sum benefits over actual or representative occupants, then compare with configuration-level electricity, financial cost, environmental effects and practicality. Shared costs are counted once.
6. Use additive-response screening as a proposed approximation, then verify interactions. John proposed coarse-to-fine interval refinement; fractions/spacings and exploration safeguards remain unselected. MILP and mixed-integer convex formulations are under consideration, with no general speed or continuous-global-optimum guarantee. See [screening and refinement](design.md#candidate-screening-before-detailed-verification).
7. For optional ducted systems, John acknowledged node temperatures and segment inlet/outlet relations. Selectable routing, shared installation costs and thermal-loss modes are [recorded proposals](design.md#optional-duct-network-and-installation-model), not mandatory bus-model features or validated engineering. Fixed/precomputed coefficients are needed for the discussed linear duct equations.

Tianyi's proposed temperature advection–diffusion equation is recorded in [design.md](design.md). It requires an airflow field; it does not calculate that field itself. Initial/boundary conditions, moisture transport and mixing assumptions remain unresolved. No final solver, coefficients, comfort function, weights or numerical result exists.

## Scope and research boundaries

- Begin with the required open-sided bus shelter; enclosure changes are set aside for now. Shade is not explicitly named as a system in the question, but solar exposure and facility design are. Holding shade fixed is a comparison proposal, not a new contest requirement.
- Do not equate stationary occupants with assigned seating or walking with narrow one-way passages. Behavior, geometry and outdoor exposure are separate inputs. Mixed and time-varying occupancy can share one framework.
- [Bus-stop research](research.md) supports climate-dependent testing rather than a universal winner. Mist prototypes differ from the source's wet-pad coolers; the latter intentionally deliver humid air, not liquid spray onto people. Singapore's ended cooled-air trial highlights placement and maintenance costs.
- [Semi-open research](research.md) retains the significant-outdoor-exchange requirement. Enclosed rooms cannot replace the required semi-open case. Documented deployments, transferable equipment principles and prototypes are distinguished.
- [Design options](design.md) retains stadium and ducted-system research. The owner's earlier exclusion of stand-alone stadium fans does not remove the required bus-shelter fan comparison. No technology or venue has been selected.

## Teammate update at first inspection

On 2026-11-07, the remote had only the initial Overleaf import (`cc664d5`): a title and empty Introduction in `main.tex`. Tianyi's PDE proposal came through chat, not that commit. Recheck remote updates before subsequent work; this is an inspection baseline, not a perpetual claim about the repository.

## Next action

Choose a compact core and optional extensions under the 25-page rule. Specify shelter geometry/scenarios, equipment and a defensible utility; check whether its screening formulation is MILP, MIQP or another class. Verify one complete small case and interaction sensitivity before scaling; add duct routing/heat gain only where material. Resolve the power-unit ambiguity. No numerical solver implementation or manuscript edit is requested by this recording task.
