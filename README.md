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
| Define four-person collaboration workflow | John / this agent | agent.md; contribution workflow in design.md and research.md; this startup/table | 70a6d65 | done | Workflow and design/research templates documented; local links/anchors, retained sources and manuscript preservation checked. Read agent.md before claiming the next task; no scientific model validation claimed. |

Next technical tasks remain unclaimed: define bus-shelter geometry/scenarios; choose airflow and temperature interfaces; define occupant exposure/benefit; verify candidate inputs and the screening approximation. Teammates should claim concrete sections before starting those edits.

## Agreed scope and decisions

Start with a simple **open-sided bus shelter**, comparing the required fan and two evaporative coolers. Enclosure changes are set aside for now. Shade is not explicitly named as a system in the problem, although facility design and solar exposure are; holding the shelter's shade fixed is a proposed comparison condition. No specific cooler or outlet arrangement has been selected.

Use four categories: **benefit to people, all financial costs, environmental effects, and nonfinancial practicality**. Reliability affects each rather than receiving a separate score. Comfort can improve toward an optimum and worsen with overcooling; health protection is distinct and needs its own justified measure. Final metrics, weights, comfort functions and safety thresholds remain undecided.

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
4. Sum benefits over actual or representative occupants, then compare with configuration-level electricity, financial cost, environmental effects and practicality. Shared costs are counted once.
5. Explore a simplified additive response model to choose candidates, then verify them with interactions included. The weak-interaction approximation is unvalidated; refine if it changes rankings. Brute-force enumeration is not the preferred general search.

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

Specify a small shelter geometry, weather/occupancy scenarios and feasible equipment choices. Choose how to estimate airflow and calibrate the candidate-screening response; validate the weak-interaction approximation before relying on it. Resolve the problem's power-unit ambiguity. No numerical implementation or manuscript editing is requested yet.
