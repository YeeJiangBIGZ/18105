---
length_reason: Retains the agreed evaluation categories and detailed candidate measures alongside current requirements, decisions and model status for team coordination.
---

# HiMCM 2026 Problem B progress

Updated: 2026-11-07. Maintain this as the current decision record rather than a running transcript.

## Agreed scope and workflow

- Source: [2026 Problem B](2026_HiMCM_Problem_B.pdf).
- General chat: HiMCM — General for coordination; separate responsibility chats may be used for verification and ideas.
- Owner requests progress to be stored as we go. This local workspace is connected to [YeeJiangBIGZ/18105](https://github.com/YeeJiangBIGZ/18105). Record plans and agreements locally and on GitHub, checking teammate updates before changes.
- Current scope hold, 2026-11-07: planning and research records only, on `codex/model-planning`. Leave `main` and `main.tex` unchanged; no merge or manuscript implementation until requested.
- Current stage: beginning mathematical formulation, starting with the required bus shelter and planning a spatial extension for the semi-open rail-station waiting area; before implementation. See [model-formulation.md](model-formulation.md) for the proposed equations, assumptions and unresolved inputs.
- Working question: How should cooling facilities be chosen, placed and operated to provide the greatest overall benefit to people, accounting for their duration of stay, cost, noise, environmental effects and other relevant factors?
- The problem first requires cooling efficiency, then an extension to overall effectiveness. Benefit per energy and a broader decision framework are candidate structures. Four evaluation categories are agreed below; no utility function, weights, safety thresholds, venues or final individual measures have been selected.

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

## Agreed evaluation categories

Owner revision, 2026-11-05: use four categories, with reliability integrated into them rather than scored separately. Practicality covers nonfinancial considerations. This replaces the earlier candidate menus; individual measures and weights remain undecided.

Benefit to people considers how much a cooling method improves comfort and heat safety, how many people benefit and for how long, and drawbacks such as noise, drafts and dampness.

Financial cost includes purchase, installation, energy, water, operation, maintenance, repairs, replacement and disposal over the system's lifetime.

Environmental effects include greenhouse-gas emissions, water and material consumption, refrigerant leakage, waste and impacts on the surrounding environment.

Practicality covers nonfinancial considerations such as space requirements, access to electricity and water, ease of installation and servicing, accessibility and equipment safety.

Reliability is integrated into these four categories through its effects on sustained human benefit, repair and replacement costs, resource waste and interruptions to normal use.

## Detailed breakdown for discussion

Owner asks for elaboration, especially the different values of ordinary cooling, overcooling and protection from dangerous heat. The following is a proposed breakdown within the four agreed categories, not an adopted equation or weighting scheme.

### Benefit to people

- Comfort improvement: assess the change from the same venue without the intervention. A proposed comfort response rises toward a comfortable range, flattens near it and falls with excessive cooling. Overcooling can leave a benefit relative to a very hot baseline while providing less benefit than appropriate cooling; from an already comfortable baseline it may produce a net loss.
- Health protection: assess reductions in heat exposure and, where supported by evidence, expected heat-related harm. Distinguish this from perceived comfort. Protection against severe harm should be considered separately from small comfort gains; the method of prioritizing it remains a team decision.
- Health outcomes: consider both probability and severity of harm. Do not claim a system prevents heatstroke or estimate cases prevented from a temperature reduction alone. A risk relationship or explicitly labeled exposure proxy is needed.
- Reach and duration: count actual beneficiaries and their exposure histories, rather than nominal cooled area alone. Comfort benefit can be accumulated over person-time; health risk may depend on duration and previous exposure nonlinearly.
- Different people: account for relevant differences in age, health, activity, clothing and exposure. Decide how to represent unequal benefits across positions and visitor groups without assuming one preferred temperature for everyone.
- Visitor drawbacks: noise, unpleasant drafts, dampness, hygiene concerns, visual intrusion and obstruction can offset useful cooling. Compare net effects without counting the same dissatisfaction twice.
- Reliability: interruptions reduce delivered comfort and protection; an outage during extreme heat may matter more than an equal-length outage during mild conditions.

### Financial cost

- Upfront cost: equipment, delivery, installation, wiring, plumbing and site preparation.
- Running cost: electricity, water, treatment products, consumables and operating staff.
- Upkeep: scheduled cleaning and servicing, inspections, unexpected repairs and parts; assign each expense once.
- Lifetime cost: durability, replacement frequency, removal, disposal and residual value over a common comparison period.
- Indirect cost, where relevant: lost usable space or revenue, installation closures and rental of backup equipment.
- Reliability: use expected repair, replacement and disruption costs rather than a separate reliability score. An idle broken device having a lower energy bill does not make it preferable; lost benefit remains in the human category.

### Environmental effects

- Operational emissions: emissions associated with energy supply; electricity price and emissions are different effects.
- Water-resource burden: quantity consumed and the local significance of scarcity.
- Refrigerants: applicable leakage impacts, with climate effects counted only once.
- Manufacturing and replacement: material use, manufacturing emissions, transport and replacement equipment.
- Waste and pollution: discarded consumables, wastewater and end-of-life equipment.
- Local surroundings: discharged heat, environmental noise and other effects outside the visitor area, where applicable.
- Reliability: premature failures may require extra materials and generate waste; wasted operation may consume resources without providing benefit.

### Practicality excluding financial cost

- Installation fit: footprint, mounting, structural compatibility, wiring, water access and drainage.
- Everyday use: whether equipment interferes with seating, queues, walking routes, wheelchair access, signs or emergency exits.
- Operating effort: supervision, refilling, cleaning, storage and seasonal setup, expressed as operational burden rather than money already counted under cost.
- Suitability for the actual venue: whether useful cooling can be delivered in its exposed or partially enclosed setting and its weather conditions; avoid duplicate scoring of performance already represented by human benefit.
- Equipment safety and hygiene: exposed moving parts, electrical exposure, wet surfaces and necessary sanitation measures, as applicable.
- Repair and adaptation: access to parts and servicing, restoring service after a failure, relocation and adding capacity.
- Reliability: ability to maintain usable service and recover from interruption. Some practicality and safety conditions may be feasibility requirements rather than tradeable utility terms.

### Evidence and modeling limits

- WHO, [Heat and health](https://www.who.int/news-room/fact-sheets/detail/climate-change-heat-and-health), accessed 2026-11-05: heat exposure can cause serious illness; vulnerability depends on individual characteristics and exposure. This supports separating health protection from comfort, not any proposed numerical weight or facility-specific risk estimate.
- UC Berkeley CBE, [Elevated air speed and thermal comfort](https://cbe-berkeley.gitbook.io/fans-guidebook/practitioner-summary/elevated-air-speed-and-thermal-comfort), accessed 2026-11-05: comfort involves air and radiant temperature, humidity, air speed, clothing and activity. Its indoor methods require an applicability check before use at an open venue.
- A comfort range, risk curve, baseline, comparison horizon and any priority given to severe harm remain unresolved. No universal optimal temperature or safety threshold has been selected.

## Current working model

Discussed structure, not a validated implementation:

1. Describe coolers and outlets by technology, capacity, position, direction, area and flow; shared outlets remain subject to equipment limits.
2. Predict local airflow, temperature and humidity for the configuration, weather and venue geometry. A side-mounted outlet was an example, not a chosen installation.
3. Represent occupants as points with arrival/departure times and paths. Constant-position paths represent stationary occupants. Integrate benefit over exposure time; distance integrals require inverse-speed weighting and separate waiting contributions.
4. Sum benefits over actual or representative occupants, then compare with configuration-level electricity, financial cost, environmental effects and practicality. Shared costs are counted once.
5. Explore a simplified additive response model to choose candidates, then verify them with interactions included. The weak-interaction approximation is unvalidated; refine if it changes rankings. Brute-force enumeration is not the preferred general search.

Tianyi's proposed temperature advection–diffusion equation is recorded in [model-formulation.md](model-formulation.md). It requires an airflow field; it does not calculate that field itself. Initial/boundary conditions, moisture transport and mixing assumptions remain unresolved. No final solver, coefficients, comfort function, weights or numerical result exists.

## Scope and research boundaries

- Begin with the required open-sided bus shelter; enclosure changes are set aside for now. Shade is not explicitly named as a system in the question, but solar exposure and facility design are. Holding shade fixed is a comparison proposal, not a new contest requirement.
- Do not equate stationary occupants with assigned seating or walking with narrow one-way passages. Behavior, geometry and outdoor exposure are separate inputs. Mixed and time-varying occupancy can share one framework.
- [Bus-stop research](bus-stop-cooling-research.md) supports climate-dependent testing rather than a universal winner. Mist prototypes differ from the source's wet-pad coolers; the latter intentionally deliver humid air, not liquid spray onto people. Singapore's ended cooled-air trial highlights placement and maintenance costs.
- [Semi-open research](semi-open-cooling-research.md) retains the significant-outdoor-exchange requirement. Enclosed rooms cannot replace the required semi-open case. Documented deployments, transferable equipment principles and prototypes are distinguished.
- [Design options](design-options.md) retains stadium and ducted-system research. The owner's earlier exclusion of stand-alone stadium fans does not remove the required bus-shelter fan comparison. No technology or venue has been selected.

## Collaboration baseline

First remote inspection, 2026-11-07: `main` at `cc664d5e1bf88d99d0096c01a12ca3eb8fb632eb` contained only `main.tex`, an initial Overleaf import by Yee Jiang with a title and empty Introduction. No other branches, open pull requests or issues were present before this planning branch. The teammate's PDE was supplied in chat, not present in that commit. Later remote work must be checked afresh. GitHub delivery does not establish Overleaf synchronization.

## Next action

Specify a small shelter geometry, weather/occupancy scenarios and feasible equipment choices; choose how to estimate airflow and calibrate the candidate-screening response. Explain assumptions before code, then verify one complete small case before scaling. Resolve the source's power units and separate fan perceived cooling from evaporative air-temperature reductions. Maintain AI-assistance provenance for eventual disclosure. Current authorization remains planning records only.
