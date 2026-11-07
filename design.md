---
length_reason: Consolidates equations, candidate evaluation factors, installation choices and the station extension as the single team design reference.
---

# Model and design

Updated: 2026-11-07. Working structure discussed with John, incorporating Tianyi's temperature-equation proposal and assistant-proposed details. No calibrated implementation, chosen solver or numerical optimum. [README.md](README.md) holds agreed scope and decisions; [research.md](research.md) holds evidence; [agent.md](agent.md) holds collaboration rules.

## Design contribution workflow

Follow [agent.md](agent.md) and claim the exact heading in [README's task table](README.md#team-startup-and-task-table). This document is the technical specification, not a transcript. Patch the relevant component; do not rewrite another person's derivation or promote a proposal to accepted without the recorded human decision.

1. **Define the component.** State the problem requirement, purpose, owner and the next component consuming its output. Declare symbols, dimensions, units, coordinate system, time basis and comparison baseline before equations.
2. **State assumptions and inputs.** Link source claims/parameters to research.md headings. Label measured, transferred, assumed and illustrative inputs separately. Explain simplifications, validity limits and what could change the result; missing calibration stays missing.
3. **Specify the calculation.** Give equations/algorithm, constraints and initial/boundary conditions where applicable. State output meaning and format. Distinguish thermal cooling power from electrical input, temperature from comfort, and time-weighted exposure from path length. New symbols or changed interfaces must be flagged to affected components.
4. **Check a small case.** Check units and relevant conservation/limits; trace one complete configuration through local conditions, occupant exposure, aggregate benefit and resources. Useful cases include zero occupancy, no intervention, overcooling, a stopped pedestrian and shared outlet capacity. For numerical methods, specify calibration, convergence and uncertainty checks before claiming validation. A surrogate's ranking must be checked against the interaction model, including some diverse alternatives.
5. **Hand off.** Record results or a precise planned check, reviewer, limitations and next action. A different teammate/agent reviews consequential claims where feasible; if none has reviewed, say so. Implementation starts only under an explicit task. Accepted decisions go into README; detailed equations remain here. Preserve superseded reasoning only when needed to explain a trade-off; Git retains history.

Use this compact component header for new or substantively revised components:

> Component / owner / requirement: …
>
> Decision: proposed | accepted (human/date) | superseded. Verification: unchecked | checked (scope/reviewer/date) | failed.
>
> Inputs and units / assumptions / linked research: …
>
> Equations and constraints / outputs and downstream dependency: …
>
> Small-case checks and result / limits / next action: …

### Component handoffs to establish

| Component | Inputs → outputs | Current status |
|---|---|---|
| Geometry, weather, cooler and outlets | Layout/settings and ambient conditions → feasible equipment boundary inputs | Proposed; dimensions and performance missing |
| Airflow, heat and moisture | Boundary inputs → spatial velocity, temperature and humidity; radiant conditions separately specified | Proposed; solver and mixing/buoyancy treatment open |
| People and benefit | Fields plus paths/dwell times and attributes → individual and aggregate comfort benefit; separate safety measure | Proposed; comfort/risk mapping open |
| Screening and optimization | Validated response approximation, constraints and scenarios → candidate configurations → detailed checks | Proposed; coefficients, search and error tolerance open |

These are dependency descriptions, not adopted numeric schemas or named assignments. Use common units/scenarios across components; agree changes at the interface before another component relies on them. No existing draft below has been independently validated merely because it appears in this document.

## Purpose and comparison boundary

Start with Problem B's three bus-shelter systems, then extend to a semi-open rail-station waiting area. Compare each configuration against the same shelter without active cooling, under matched weather, occupancy and observation period. Hold shade and geometry fixed unless deliberately evaluating changes to them. The freezer analogy motivates measuring useful service maintained, rather than treating low electricity consumption alone as efficiency.

A configuration includes technology, number/capacity of units, placement or outlet layout, and operating schedule/settings. The first bus comparison can hold placement and schedule fixed to avoid an unnecessarily large optimization problem.

## Physical conditions to comfort

For zone j, time step t, and configuration k, estimate air temperature T, humidity RH, air speed v and mean radiant temperature Tr. A mapping theta = F(T, RH, v, Tr; clothing, activity) supplies a common equivalent thermal-condition scale. F remains unselected: its validity for outdoor conditions and brief waiting exposures must be checked. It is not simply air temperature or an assumed subtraction of the problem's listed cooling maxima.

Thermal comfort involves these environmental and personal factors; see [CBE's elevated-air-speed guide](https://cbe-berkeley.gitbook.io/fans-guidebook/practitioner-summary/elevated-air-speed-and-thermal-comfort), read 2026-11-06. This supports the factors, not a specific outdoor calibration or the penalty proposed below.

Candidate dimensionless discomfort penalty:

    D(theta) = [max(theta - theta_H, 0)/s_H]^2
             + [max(theta_L - theta, 0)/s_L]^2

theta_L and theta_H bound a proposed comfortable interval; positive s_H and s_L set hot/cold penalty scales in the same units as theta. Within the interval D=0; either excessive warmth or excessive cooling raises D. This is an explicit mathematical preference assumption, not an established physiological law. The team must choose/calibrate its shape and parameters or replace it with a supported satisfaction measure. Squared versus linear penalties should be checked for ranking sensitivity. Different groups can have different parameters.

## Delivered benefit and efficiency

Let N_jt be the mean number of people in zone j during time step t, and let dt be its duration in hours. Let D_0jt and D_kjt be discomfort without active cooling and with configuration k. Initially assume the same population and distribution in both scenarios.

    B_k = sum_j sum_t N_jt (D_0jt - D_kjt) dt
    E_k = sum_t P_kt dt
    eta_k = B_k / E_k, for E_k > 0

B has units of discomfort-point person-hours; E is kWh when total electrical power P is in kW. eta is a service-efficiency index, not thermodynamic COP or a percentage. Negative contributions are retained when cooling worsens comfort. Count all system electricity, including auxiliary fans and pumps. The no-active-cooling reference has B=0; if E=0 its ratio is undefined and should not be assigned a fictitious efficiency.

For a constant, single-zone case this reduces to B=N(D_0-D_k)H, E=P H and eta=N(D_0-D_k)/P. Uniform conditions apply only within an assumed served zone; unserved occupants have zero intervention benefit, not the same benefit as those beside an outlet.

Illustrative arithmetic only: ten people present for one hour, each receiving a 0.2-point discomfort reduction, give B=2 point-person-hours. At 0.5 kW, E=0.5 kWh and eta=4 point-person-hours/kWh. This verifies units, not real equipment performance. Empty occupancy gives B=0; no change in comfort gives B=0; worsening comfort gives B<0. Doubling duration at steady conditions doubles B and E without changing eta.

## People as points, exposure along paths

The working representation discussed with John is a cooler, its outlets and occupants. For cooler k use technology, position, capacity and a performance map linking weather/settings to supply conditions, electricity and water. Outlet i has a supplying-cooler index, position, direction, area, shape and volume flow. These are constrained physical quantities, not independent free sources of cooling.

Person p has arrival/departure times and trajectory r_p(t); their speed is ||d r_p/dt||. A stationary person has constant position during the stay. With matched baseline and intervention paths, benefit is:

$$
B_p(X)=\int_{t_p^{\mathrm{in}}}^{t_p^{\mathrm{out}}}
\left[D_{p,0}(t)-D_{p,X}(t)\right]dt,
\qquad B(X)=\sum_p w_p B_p(X).
$$

Here X is the configuration; D is discomfort based on local conditions and personal attributes. Weight w_p is one for an individual, or the number of people represented by a representative path. The time integral captures stops and movement. For moving segments parameterized by distance s, dt=ds/v_p(s) and the equivalent line integral is integral of Delta D_p(s,t_p(s))/v_p(s) over ds. Use separate time contributions for stops; never divide by zero speed. An unweighted distance integral does not measure exposure duration.

Zone occupancy and path integration are alternative aggregation methods and should not both be counted for the same occupants. Path-history dependence may be needed for transient comfort or health; adding instantaneous discomfort reductions is a starting assumption. Actual tracking of every visitor is not required if representative locations/paths and dwell times adequately capture the comparison.

## Candidate screening before detailed verification

John favors a structured search over exhaustive configuration enumeration. The discussed direction is to use a simplified response model to identify several promising designs, then evaluate them with a physical model that includes interactions. Weak outlet interaction is a proposed screening assumption, not established physics or permission to ignore interactions in the final assessment.

For fixed candidate outlet positions and directions, a proposed approximation is:

$$
\theta_{jt}(\boldsymbol{x})\approx\theta^0_{jt}-\sum_i a_{jti}x_i.
$$

Here x_i is an outlet operating level, a_jti its estimated influence at section j/time t, and theta an as-yet-unselected thermal-condition measure. Coefficients require simulations, data or justified physical estimates; they are weather/layout dependent. The expression does not replace the temperature PDE as an exact law or imply exact superposition of independent air jets. Interactions can arise without geometric stream intersections.

With affine predicted conditions, a convex squared comfort-band penalty, fixed occupancy and linear feasibility constraints, minimizing aggregate discomfort can be expressed as a convex quadratic program. Maximizing comfort benefit is equivalent only when the baseline is fixed. This statement concerns the proposed surrogate; nonlinear equipment performance, a benefit/energy ratio or other constraints may change the optimization class. Binary outlet-installation choices make the corresponding problem mixed-integer, without a general fast-solution guarantee. Arbitrary positions/directions require discretization or a further optimization method.

Workflow: calibrate/validate an approximation, search for candidates, evaluate with interactions, and refine if rankings change. Check a few diverse alternatives outside the surrogate's best set because model bias can exclude good designs. No solver, coefficients, candidate spacing, numerical objective weights or validity tolerance has been selected.

## Bus-stop installation compatibility

John's question; proposed, not adopted. Binary logic checked algebraically by this agent; site validation and independent review pending. No solver run or actual conflict list.

For technology/location/size/orientation option i, let z_i in {0,1} indicate installation. Incompatible pairs E obey:

$$
z_i+z_j\leq1\quad\text{for each }(i,j)\in E.
$$

This allows (0,0), (1,0), (0,1), but excludes (1,1). Hypothetical example: left compact A, rear large B, right compact C. If B conflicts with both, impose z_A+z_B<=1 and z_B+z_C<=1. A and C remain compatible: conflicts are not transitive. Actual edges require footprint, access, mounting or equipment evidence. Crossing jets/overlapping coverage alone are not prohibitions.

At one exclusive mounting slot S, sum_{i in S} z_i<=1. Independent units with fixed demands P_i obey sum_i P_i*z_i<=P_available; costs have an analogous budget limit. A group can overload a resource even if each pair fits. Shared outlets need plant-capacity accounting. Adjustable settings obey 0<=x_i<=x_i_max*z_i.

With additive benefit max sum_i b_i*z_i, these are binary/mixed-integer linear constraints and objective. Benefit additivity is an unvalidated screening assumption, not exact airflow physics. The earlier squared discomfort objective gives a mixed-integer quadratic model under affine response assumptions; exclusions work there too. No general speed guarantee. Keep the required fan/two-evaporative comparison. Next define sites, clearances, capacities and justified conflicts.

## Safety and overall effectiveness

Report total B alongside eta: high benefit per kWh need not mean enough benefit. Keep a separate justified heat-exposure measure or risk model; discomfort is not a medical risk estimator. Thresholds, duration effects and vulnerable groups require evidence. Do not claim heatstroke prevention from D or temperature reduction alone.

For the later effectiveness extension, compare human benefit/safety/visitor drawbacks, lifecycle financial cost, environmental effects and nonfinancial practicality. Initially show trade-offs and feasibility constraints without arbitrary aggregate weights. Put all monetary energy/water costs in financial cost; physical emissions and water-resource burden belong to environment. Reliability changes delivered conditions, costs and other outcomes rather than adding a fifth score. Minimum benefit or safety requirements remain proposals, not chosen thresholds.

## Multiple outlets and outdoor wind: formulation proposal

Tianyi proposed the temperature advection–diffusion equation in a screenshot shared by John on 2026-11-07:

$$
\frac{\partial T}{\partial t}+\mathbf u\cdot\nabla T=\alpha\nabla^2T+S.
$$

It predicts temperature given an airflow field; it is not an airflow solver. Initial temperature, inlet/outdoor conditions and surface heat transfer must be specified. S has temperature/time units; volumetric heat input q'''/(rho*c_p) gives that form. Represent supply air through inlet temperature/flow, or justify a distributed approximation without double counting. Molecular diffusivity alone does not capture turbulent mixing; any effective diffusivity or closure needs justification. Evaporative systems also require moisture inputs/transport. Buoyancy can require coupled airflow/temperature calculation; neglecting it must be explicit. No solver or closure is adopted.

Outlet i has position r_i=(x_i,y_i,z_i), unit direction d_i, area A_i, shape/spread and volume flow Q_i, with discharge speed U_i=Q_i/A_i for uniform normal discharge. Supply temperature/moisture and shared flow/cooling capacity are constrained by the cooler. Duct resistance, heat gain/leakage and auxiliaries affect power and performance. Adding outlets is not free capacity; redesigning a standalone cooler into ducts changes the original device assumptions. The previous side-mounted example is not a selected layout.

Outdoor wind is a scenario input, not a design control. Test calm and several directions/speeds, assigning probabilities only with justification. Keep one fixed installation across scenarios; adaptable settings require actual control capability. The resulting local fields include a single velocity vector, temperature and moisture. Independent jets or temperature reductions generally cannot be summed exactly: entrainment, pressure, turbulence, obstacles and deflection cause interactions, even without visible intersections. Opposing streams can redirect and mix. A well-mixed section alone cannot resolve directional jets.

Start with a few layouts and mean-wind scenarios. Retain three dimensions when comparing outlet heights. A justified empirical jet approximation may screen weak interactions; stronger interactions require more detailed checks or CFD. CFD itself needs boundary-condition, turbulence and mesh validation. Writing a predictor symbol is not solving the physical model.

Sources read 2026-11-07: [NASA fluid equations](https://www1.grc.nasa.gov/beginners-guide-to-aeronautics/navier-strokes-equation/) and [NIST local CFD versus uniform zones](https://www.nist.gov/publications/using-cfd-capabilities-contam-30-simulating-airflow-and-contaminant-transport-and). These establish method distinctions, not validated shelter predictions.

## Rail-station extension and missing inputs

Behavior, geometry and outdoor exposure are separate inputs. Stationary occupants need not have assigned seats; circulation can be broad, bidirectional or crossing. Narrow shelters/queues, broad plazas and covered markets are counterexamples to treating stationary areas as broad seated spaces and walking areas as narrow one-way passages. A location can change use over time. [Network Rail guidance](https://www.networkrail.co.uk/wp-content/uploads/2023/12/NR-GN-CIV-100-03-Station-Capacity-Planning-guidance.pdf), sections 3.5/3.7, treats concourse waiting/circulation and one-/two-way passages; [NYC DOT plazas](https://www.nyc.gov/html/dot/html/pedestrians/nyc-plaza-program.shtml) combine circulation, seats, markets and events. Read 2026-11-06; these are mixed-use evidence, not cooling measurements.

Use distinct occupancy/movement rules within one thermal/benefit framework. Sections exchange people, air, heat and moisture; independently optimizing them requires negligible coupling or explicit treatment of shared plant/budget. Fixed occupancy across alternatives is a proposed simplification; test sensitivity to people gathering near cooling when relevant. Do not double count visitors. Representative counts/paths may suffice; detailed pedestrian simulation is not required. Individual histories may matter for safety.

Extend to connected occupied sections with calibrated or physical performance estimates. Deep mall interiors with little outdoor exchange and fully enclosed refuge rooms cannot replace the required semi-open case. Before numbers: choose a defensible comfort mapping, geometry, weather, occupancy/dwell times, coverage and equipment performance. The listed fan effect is perceived, evaporative effects are air-temperature changes, and all are maxima. Treating the source's kW/hr figures as average kW remains an explicit unresolved assumption; dividing the listed temperature numbers by power is not a justified ranking.

Source: original Problem B, repeatedly reread through 2026-11-07. AI assistance includes notation, equations, interpretation, limiting checks and drafting; this does not imply independent team derivation.

## Candidate measures within the four agreed categories

These are options for selection, not adopted weights or a final score.

- **Human benefit:** comfort improvement from a matched baseline, including diminishing benefit and overcooling; separate heat-exposure/risk reduction; actual coverage and person-time; differences in vulnerability, activity and clothing; noise, drafts, dampness, hygiene, visual intrusion and obstruction. Avoid counting the same dissatisfaction twice. Outages reduce benefit, and their timing matters.
- **All financial costs:** equipment, delivery, installation, wiring/plumbing and site preparation; electricity, water, treatment, consumables and staff; cleaning, servicing, inspection, repairs and parts; replacement, removal, disposal and residual value over a common horizon. Include lost space/revenue, closures or backup rental only where relevant. Count each expense once; low energy bills during failure are not success.
- **Environmental effects:** operational and embodied emissions, local water scarcity, refrigerant leakage, materials, manufacture/transport/replacement, wastewater, consumables and end-of-life waste; external heat discharge and environmental noise. Separate physical impacts from their monetary prices; count refrigerant climate impacts once. Premature failures add resource use and waste.
- **Nonfinancial practicality:** footprint, mounting, structure, utilities/drainage, access routes, seating, signs and emergency exits; supervision, refill/cleaning/storage and seasonal burden; equipment safety, wet surfaces and sanitation; parts/service access, recovery, relocation and scaling. Some conditions are feasibility constraints. Do not rescore cooling performance or monetary labor cost here.

Reliability affects these outcomes rather than adding a fifth category. A comfort range, safety threshold, response curve and priority weighting remain open. Severe health protection must not be inferred from a temperature reduction alone. [WHO heat and health](https://www.who.int/news-room/fact-sheets/detail/climate-change-heat-and-health) supports separating vulnerability and health from comfort; [CBE](https://cbe-berkeley.gitbook.io/fans-guidebook/practitioner-summary/elevated-air-speed-and-thermal-comfort) identifies environmental/personal comfort factors, with an outdoor applicability check still required.

## Technology and installation options

### Definition of a system

A design specifies cooling technology, number and size of units, supply outlet locations and directions, supporting site modifications, utility and distribution connections, heat rejection where applicable, and operating rules. The cooling plant and the outlets delivering cooling need not be at the same location.

### Technology candidates

| Technology | Mechanism and implementation | Main design issue |
|---|---|---|
| Fans | Ceiling, wall, column or pedestal fans move air over occupants | Airspeed at occupied locations, coverage and draft/noise effects; fan output is not an air-temperature reduction |
| Direct evaporative coolers | Fan blows air through wetted media | Climate-dependent evaporation, added moisture, water supply and cleaning |
| Indirect evaporative coolers | Separate wet air stream cools supply air through a heat exchanger | Does not directly add moisture to supply air; requires more equipment and a separate exhaust path |
| Mist systems | Overhead or perimeter nozzles disperse water for evaporation, optionally with fans | Wind drift, evaporation conditions, hygiene and avoiding unwanted wetting |
| Refrigerated air cooling | Split units, ducted outlets or fan coils supplied by a chiller | Electricity, cooled-air escape, condensate drainage and placement of heat rejection |
| Radiant cooling | Chilled panels above or beside occupied areas exchange radiant heat with people | Chilled-water source, panel exposure to occupants and condensation management; outdoor membrane systems are a research-backed extension |

Direct/indirect evaporation: [UK Energy Technology List](https://etl.energysecurity.gov.uk/products/heating-ventilation-air-conditioning-hvac/evaporative-air-coolers). Fans: [CBE guidebook](https://cbe-berkeley.gitbook.io/fans-guidebook). Mist: [University of Melbourne demonstration](https://research.unimelb.edu.au/strengths/updates/impact/mist-demonstrates-a-context-aware-outdoor-urban-cooling-system). Refrigeration: [PNNL](https://basc.pnnl.gov/resource-guides/air-conditioning). Outdoor radiant cooling: [UBC Cold Tube](https://sala.ubc.ca/research/the-cold-tube/).

### Layouts to compare

- Overhead row or grid: fans, diffusers or panels distributed over benches, queues or waiting zones.
- Side or column mounting: directional units aimed into occupied areas; compare heights and angles.
- Local cooling stations: small cooled islands at benches or designated rest areas.
- Distributed outlets: one remote plant feeding several outlets through ducts or water pipes.
- Mobile units: portable devices for varying crowd locations, with routes for cables, hoses and hot exhaust if applicable.

Specify each unit or outlet by horizontal position, mounting height, direction and output setting. Compare one large unit with multiple smaller units and targeted coverage with broad coverage. Nominal floor coverage alone is insufficient: airflow, obstacles, prevailing wind and actual occupancy must be considered. Layouts are proposals, not established rankings.

### Supporting design choices

- Shade roofs, screens, trees and suitable roof treatments to reduce solar exposure; check sun angle and occupied locations. [EPA heat-island guidance](https://www.epa.gov/heatislands/guide-reducing-heat-islands)
- Partial wind screens to test whether cooled air remains useful longer without unacceptable loss of ventilation or accessibility; effects are site-dependent.
- Ducts and adjustable diffusers to place air outlets near intended users while locating noisy equipment elsewhere; include fan pressure losses and duct heat gains.
- Chilled-water pipes to serve fan coils or radiant panels; include pumps, pipe insulation, heat gains and condensation management.
- Refrigerant lines between the cooling coil and condensing equipment; these are distinct from heat pipes.
- Heat rejection: place condenser discharge away from occupied zones and supply-air intakes; assess actual exhaust recirculation rather than assuming all outdoor positions are equivalent.
- Water supply, treatment, drainage, safe electricity routing and maintenance access.
- Operating choices: schedules, occupancy detection, adjustable airflow, climate-dependent enable/disable rules and separate settings for occupied zones.
- Optional thermal storage: ice or chilled water can move some cooling production to other hours; include charging energy and losses rather than assuming energy savings. [DOE thermal storage overview](https://betterbuildingssolutioncenter.energy.gov/resources/combined-heat-and-power-technology-fact-sheet-series-thermal-energy-storage)

### Heat pipes

A conventional heat pipe is a sealed device using evaporation and condensation to transport heat from a warmer end to a cooler end. It requires a suitable heat sink and does not independently create a cold source or pump heat uphill in temperature. [NASA thermal control, heat pipes](https://www.nasa.gov/smallsat-institute/sst-soa/thermal-control/)

Possible uses to investigate include transferring heat from a component or surface to a cooler sink, and heat recovery around an air-conditioning coil for humidity control. A dehumidification heat pipe can precool incoming air and reheat outgoing air; this is not automatically an increase in delivered cooling or overall efficiency. [DOE technical discussion](https://www.energy.gov/eere/buildings/articles/2014-08-28-issuance-energy-conservation-standards-packaged-terminal-air)

Do not specify an outdoor heat-pipe cooling scheme without identifying the sink temperature, heat-transfer capacity and how the sink rejects the received heat. If the intended meaning of heat pipes is pipes distributing chilled water or refrigerant, model those distribution systems under their actual names.

### Cooling source versus delivery arrangement

Clarification for the design model: under-seat ports deliver ordinary conditioned air to spectators; refrigerant stays in its equipment circuit. The reviewed examples do not establish that most open stadiums use under-seat cooling.

Two independent choices must be represented:

1. Production and distribution architecture: a central air-handling arrangement feeding ducts; a central chilled-water plant feeding several local air-handling units; or independent local cooling units. A central plant can contain multiple chillers. Chilled water exchanges heat with air through coils and returns warmer to the plant; the water is not sprayed through the spectator outlets.
2. Delivery position: under/beside seats, large pitch-side jets, wall/column/overhead outlets, or local rest-area units. Fans, misting and radiant panels are additional mechanisms with different requirements; they should not be labeled equivalent forms of refrigerated-air delivery.

A generic chilled-water system can be represented as: chiller -> chilled-water pipes -> local coil and fan -> air ducts -> spectator outlets, with a water return loop and heat rejection at the plant. This is an engineering schematic, not an as-built diagram of any named stadium.

[ASHRAE air handling and distribution](https://handbook.ashrae.org/handbooks/S20/IP/s20_ch04/s20_ch04_ip.aspx) describes central refrigeration plants, distributed air handlers, chilled-water and direct-expansion alternatives. [NLR air-handling-unit reference](https://hvacresourcemap.nlr.gov/commercial-hvac/all-systems/air-water-distribution/ahu) explains water/refrigerant-to-air heat exchange through coils.

The modeled design should distinguish plant location, air-handler location and final outlet location; they need not coincide. These options remain proposals for comparison, with no layout selected.

### Ducted evaporative cooling proposal

Discussed 2026-11-06; not selected. The owner asks whether mist-bearing air can be distributed through ducts. Engineered spray sections can evaporatively cool air inside an air handler. Provide evaporation distance, droplet capture where required, drainage, water treatment and humidity control; supply cooler humid air through downstream ducts rather than assuming liquid droplets can travel through arbitrary ductwork without depositing. Water vapor and suspended liquid mist are different phases. Another candidate is piping water to mist nozzles at the final delivery locations, so evaporation occurs near the occupied zone. The latter needs wind, wetting and exposure evaluation.

For the model, include added fan power from duct resistance, water/pump use, heat gain and leakage, supply humidity, and useful benefit at occupants. The problem's standalone cooler power figures do not establish the power of a redesigned ducted installation.

Sources: [UK evaporative cooler definitions](https://etl.energysecurity.gov.uk/products/heating-ventilation-air-conditioning-hvac/evaporative-air-coolers); [Condair duct absorption and carry-over guidance](https://www.condair.de/downloads/10-point-guides/10-point-guide-to-specifying-humidifiers-en-rt.pdf); [CAREL droplet-separator description](https://www.carelparts.com/amfile/file/download/file/2230/category/2205/). Manufacturer dimensions apply to their specified equipment, not as universal design rules.

## Station comparison planning

### Proposed comparison for requirement 2b

Retain the significant outdoor exchange of a roofed, partly enclosed waiting area. Define the same weather, occupancy and waiting-time scenarios for each candidate. The following is a proposal for selection:

1. Reference: existing shelter/shade and ventilation with no added active cooler; use measured or justified baseline conditions.
2. Local refrigerated cooling: several spot units serving benches or queues, with specified heat rejection and drainage.
3. Distributed ducted cooling: centralized or sectional AHUs supplying selected occupied zones; model losses through openings rather than assuming indoor performance.
4. Evaporative cooling: retain the problem's technology family and evaluate climate sensitivity; mist is an optional separate variant.
5. Optional extension: radiant cooling around a resting zone, clearly identified as a research-based design.

Fan-assisted or hybrid options can be evaluated if selected; they are documented station practice and are not automatically uncomfortable. Enclosed refuges are supplementary scenarios, not substitutes for modeling the semi-open waiting area. Roof/shade changes and air-exchange controls should be explicit modifications relative to the baseline.

### How the bus model would need to change

Add spatially varying occupancy/paths, outdoor and relevant train-induced exchange, surges/dwell times and shared plant energy (compressors, fans, pumps, controls). Combine temperature, radiation, humidity and airflow into human outcomes, separating comfort from safety. Distinguish measurements, deployments, prototypes, estimates and proposals. No station ranking follows without geometry, weather, occupancy, performance, prices and a benefit measure.
