---
length_reason: Consolidates equations, candidate evaluation factors, installation choices and the station extension as the single team design reference.
---

# Model and design

Updated: 2026-11-09. Working structure discussed with John, incorporating Tianyi's temperature-equation proposal and assistant-proposed details. Four venues are selected; reconstruction details below remain proposals. No calibrated implementation, chosen solver or numerical optimum. [README.md](README.md) holds agreed scope and decisions; [research.md](research.md) holds evidence; [agent.md](agent.md) holds collaboration rules.

## Design contribution workflow

Follow [agent.md](agent.md); claim exact headings in [README](README.md#team-startup-and-task-table). This is a current specification, not a transcript. Preserve concurrent work and distinguish proposed/accepted/superseded decisions from unchecked/checked/failed verification. Human acceptance is not physical validation.

For each component record: owner and requirement; input units, coordinates, time basis and baseline; measured/transferred/assumed inputs with research links; equations and outputs; assumptions/limits; small-case checks, reviewer and next action. Check conservation, zero intervention/occupancy, overcooling, stopped pedestrians and shared capacity as applicable. Declare calibration/convergence needs; compare surrogate rankings with interaction-aware calculations and diverse alternatives. No implementation without an explicit task; preserve AI provenance. Git retains superseded detail.

### Component handoffs to establish

Geometry/weather/equipment → feasible boundary inputs → airflow/temperature/moisture and radiant conditions → people/benefit → verification → optional search. All interfaces remain proposed; use common units and scenarios and agree changes before another component relies on them. Geometry/performance, solver/closure, comfort mapping and screening coefficients remain unresolved; no named lane assignments or independent validation implied.

## Selected venue reconstruction plan

John accepted Dhoby Ghaut Airbitat shelter, Expo MRT elevated EWL platform, Japan National Stadium and Cartuja Qanat Ágora on 2026-11-09. The following is the general-chat agent's **proposed** minimal reconstruction and handoff, based on the [four-venue evidence dossier](research.md#selected-four-venue-evidence-dossier). Selecting a real venue does not adopt every dimension, equipment claim or operating assumption. No model geometry is implemented by this research update.

| Case / first domain | Retain in a rough model | Simplify initially | Gate before claiming a site-specific result |
|---|---|---|---|
| Dhoby Ghaut: historical shelter plus surrounding air | Roof, screens/posts, benches, open boarding side, nearby relevant obstacles; distinguish 2018 and 2019 layouts | Representative seated/standing/walking occupants; omit decorative detail | Reconcile site footprint with photos; label inferred dimensions; obtain outlet and matched weather inputs |
| Expo: occupied platform strip with its roof and outside buffer | Roof section, elevation, edge barriers/doors, columns, access openings and track-side exchange | Train-present/absent steady snapshots; representative queue and movement zones | Resolve roof-length discrepancy before whole-platform scaling; verify usable floor dimensions and openings |
| Tokyo: coarse bowl plus selected occupied sectors | Tier slope, roof shade, concourse/rear openings, differing windward/leeward exposures | Equivalent seat/crowd obstruction; limited fan modes | Establish sector boundaries from broader flow or defensible prescribed conditions; verify fan data before scaling |
| Seville Ágora: roofed sunken plaza and entrances | Floor/avenue levels, barriers, roof and openings; separate adjacent amphitheater | Simple occupant zones; existing active plant off for a fan-only comparison | Inspect full sections/height datum; define whether cooling/storage systems are disabled or explicitly costed |

**Common comparison boundary.** The selected venues provide geometry, climate and evidence. The first proposed comparison holds their passive geometry/shade fixed and evaluates ordinary fans and the small/large wet-pad alternatives. Existing hybrid cooling is not automatically included in the baseline. If an existing system remains on, account for its contribution and all relevant electricity/water in both the reference and intervention consistently. Treat observed Airbitat/Qanat performance as evidence about those specific systems, not calibration data for different devices without a transfer argument.

**Common input/output contract.** Inputs are geometry with a coordinate system and north direction; dated simultaneous outdoor temperature, RH, wind and solar conditions; surface/radiant assumptions; outlet flow, temperature, moisture and equipment power; occupancy locations/paths and dwell weights. Outputs are occupied-zone mean velocity, fluctuation statistics if predicted, temperature, RH and radiant conditions, followed by person-time benefit and configuration-level resource use. Mark every input measured, design-specified, transferred or estimated, with the source ledger in research.md. Do not infer instantaneous occupancy from capacity or daily entries.

**Keep the first evaluator small.** Start with a few representative weather/occupancy snapshots and the required device classes at declared feasible positions. Compare the same people and time interval against the no-active-cooling reference. Test domain/resolution sensitivity and mass/energy consistency; compare temperature/RH trends with matching evidence where possible. Field validation remains partial where wind or radiation is unavailable. Geometry and placement sensitivity are more defensible than unsupported extra precision.

**Scaling and optional complexity.** Validate the bus case first. Expo adds mixed waiting/movement and track-side exchange; Tokyo adds multiple exposure sectors; Seville adds a contrasting climate and enclosure geometry. Full train transients, every spectator's body, detailed stadium louvres and Qanat thermal storage are optional unless omitting them changes the question being answered. Repeated stadium sectors require matching boundary conditions and shared-resource accounting. Optimization remains a later limited extension; the four-site selection does not require four complete CFD/optimization projects within 25 pages.

**Next concrete task:** reconstruct one version of the historical bus shelter with a parameter/uncertainty table, then obtain one matched weather episode and consistent specifications for the three required device classes. The earlier standard-based 9 × 3 m illustration remains a concept. Expo geometry reconciliation and full Qanat-paper access can proceed as separate claimed research tasks. No new numerical thresholds, solver or assumptions are accepted merely by this entry.

## Complexity and the 25-page paper

**Accepted instruction: John, 2026-11-07.** Develop enough detail to understand accuracy now, but do not let the model become unnecessarily complicated. If the paper cannot fit within 25 pages, simplify the model and remove nonessential extensions to favor mathematical elegance and clear explanation. Do not treat every discussed mechanism as mandatory implementation. Retain the contest's required comparisons and deliverables; the page limit covers the full counted submission, not just model derivations.

Working reduction procedure (agent proposal): maintain a compact core and optional extensions; compare decision/benefit changes before dropping consequential physics. Use explicit assumptions where a simpler model is adequate. Routing optimization, detailed duct modes, body-resolved airflow and fine placement refinement are candidates for reduction, not automatic requirements. No particular feature has been approved for removal and no page allocation is fixed. A short explanation, valid units and one checked end-to-end case take priority over adding machinery.

## Purpose and comparison boundary

Start with Problem B's three bus-shelter systems, then extend to a semi-open rail-station waiting area. Compare each configuration against the same shelter without active cooling, under matched weather, occupancy and observation period. Hold shade and geometry fixed unless deliberately evaluating changes to them. The freezer analogy motivates measuring useful service maintained, rather than treating low electricity consumption alone as efficiency.

A configuration specifies technology, capacity, layout and operation. The first bus comparison may hold placement/schedule fixed for simplicity.

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

**Working direction accepted by John, 2026-11-07:** simple body obstacles (boxes/cylinders) with a few surrounding exposure points; retain point trajectories for bookkeeping. Average local penalties, not front/back velocity vectors. Freeze occupancy snapshots when estimating response coefficients so the screening map can remain affine; this does not validate superposition. Initially omit anatomical detail/body heat, then test sensitivity. Sample surrounding air, not zero no-slip wall velocity. See [obstruction evidence](research.md#occupant-obstruction-and-thermal-plumes).

Person p has arrival/departure times and trajectory r_p(t); their speed is ||d r_p/dt||. A stationary person has constant position during the stay. With matched baseline and intervention paths, benefit is:

$$
B_p(X)=\int_{t_p^{\mathrm{in}}}^{t_p^{\mathrm{out}}}
\left[D_{p,0}(t)-D_{p,X}(t)\right]dt,
\qquad B(X)=\sum_p w_p B_p(X).
$$

Here X is the configuration; D is discomfort based on local conditions and personal attributes. Weight w_p is one for an individual, or the number of people represented by a representative path. The time integral captures stops and movement. For moving segments parameterized by distance s, dt=ds/v_p(s) and the equivalent line integral is integral of Delta D_p(s,t_p(s))/v_p(s) over ds. Use separate time contributions for stops; never divide by zero speed. An unweighted distance integral does not measure exposure duration.

Zone occupancy and path integration are alternative aggregation methods and should not both be counted for the same occupants. Path-history dependence may be needed for transient comfort or health; adding instantaneous discomfort reductions is a starting assumption. Actual tracking of every visitor is not required if representative locations/paths and dwell times adequately capture the comparison.

### Walking flow and snapshot averaging

Recorded 2026-11-07: John supports sampling multiple segments/moments and averaging. The time-snapshot interpretation below was explained by the assistant; sampling frequency and independent steady-state validity remain unverified.

For steady arrival flow lambda, path length L and speed v>0, mean occupancy is N_bar=lambda*L/v; in section j, N_bar_j=lambda_j*Delta_s_j/v_j under steady flow and uniform section speed. Branches need local flows; pauses/queues and bus-arrival pulses need dwell-time/time-varying treatment. Fractional occupancy is an expectation, not a fractional solid obstacle. Illustrative: 6 people/minute crossing 12 m at 1.2 m/s gives one person on average.

Calculate total benefit rate R_k for each snapshot and its represented duration Delta_t_k:

$$
B\approx\sum_kR_k\Delta t_k,\qquad
\bar R=\frac{\sum_kR_k\Delta t_k}{\sum_k\Delta t_k}.
$$

Equal durations allow an arithmetic mean. Sample quiet/busy states with correct time/probability weights and matched scenarios across designs. Calculate utility before averaging; nonlinear utility and obstruction generally prevent averaging positions/fields first. Do not double count path and snapshot person-time.

Independent steady snapshots require airflow/thermal/moisture adjustment fast relative to changing inputs; otherwise use transient evolution. Test sampling convergence, pulses and ranking stability. Utility points can coexist with simple airflow obstacles/heat sources; see [occupant evidence](research.md#occupant-obstruction-and-thermal-plumes). No negligible-obstruction conclusion or numerical tolerance is adopted.

## Candidate screening before detailed verification

**Priority revised by John, 2026-11-08:** evaluate first; optimization is secondary and should explore methods beyond MILP. The earlier convex-programming preference applies to that optional route, not as a prerequisite for the evaluator. No artificial preferred wind direction or forced utility segmentation. Spatial refinement remains separate; additive responses are unvalidated.

Earlier unvalidated screening alternative: T_j≈T_j^0−sum_i a_ji*x_i; u_j≈u_j^0+sum_i b_ji*x_i, with 0<=x_i<=x_i_max*z_i and binary z_i. Coefficients are baseline-relative, weather/geometry-dependent; ambient counted once. Neglected mixing/jet interactions require checks. This is not the proposed whole-layout heuristic.

### Convexity and direction-independent wind penalty

Affine conditions and convex discomfort give concave benefit against a fixed baseline. Depending on constraints, quadratic penalties yield MIQP or mixed-integer conic models. Nonlinear comfort/efficiency ratios can change the class; binaries preclude runtime guarantees.

Preferred-vector penalty ||u-u*||² is superseded: it imposes directional comfort. Preferred-speed penalty (||u||-v*)² is nonconvex for v*>0: u=±v*d both give zero, their midpoint gives positive penalty. Scalar-speed convexity does not survive this norm composition. A symmetric convex penalty cannot favor both opposite velocities over zero.

**John's ceiling proposal; formulation below proposed, uncalibrated:** no wind penalty up to v_max, then a continuous increasing penalty. Two convex choices are:

$$
P_w(\mathbf u)=\lambda[\|\mathbf u\|_2^2-v_{\max}^2]_+,
\qquad\text{or}\qquad
P_w(\mathbf u)=\lambda[\|\mathbf u\|_2-v_{\max}]_+^2.
$$

Both require lambda,v_max>=0 with consistent units. First form: p>=0, p>=sum_c u_c²-v_max², minimize lambda*p. This is convex quadratic/conic, not MILP; no extra binaries. Subtracting v_max² avoids a jump. Second form penalizes squared excess speed. Neither is a linear fit; growth differs, and thresholds/weights remain unselected.

Fan cooling benefit remains unresolved. Fixed local direction/scalar speed is unadopted. A norm upper bound works for minimized penalties but can inflate speed rewards. Exact direction-independent speed rewards generally break convexity in unrestricted vectors.

### Noise penalty

**Form accepted by John, 2026-11-07; uncalibrated.** For person-time sample j and fixed equipment operating modes z_i:

$$
q_j=10^{(L_j^0-L_j^{lim})/10}+\sum_i10^{(L_{ji}-L_j^{lim})/10}z_i,
\qquad P_{N,j}=\lambda_N[q_j-1]_+.
$$

L^0 is ambient noise, L_ji the source-only level at the receiver, and L^lim a comfort threshold (dBA). q is normalized mean-square sound pressure; approximately uncorrelated sources are assumed. Do not add dB values or count ambient noise twice. Coefficients are precomputed, not exponentials of decisions. Minimized penalty uses p_j>=0, p_j>=q_j-1 and lambda_N*p_j: linear constraints, no extra binaries. Aggregate baseline-minus-intervention penalties with person-time weights. This energy-based annoyance surrogate is not a perception law or hearing-risk measure; calibrate source levels, threshold and nonnegative weight and check ranking sensitivity. [FHWA acoustical guidance](https://www.fhwa.dot.gov/ENVIRonment/noise/noise_barriers/design_construction/design/design03.cfm), decibel addition, read 2026-11-07, supports energy addition, not this utility choice. No equipment noise data selected.

### Adaptive outlet placement search

**Proposed 2026-11-09: multi-start variable-neighborhood search.** Secondary to evaluation; ordinary/evaporative fans only, including small/large sizes. X specifies sites, types/sizes, directions and modes; off/removal allows variable counts.

1. Use a coarse feasible site grid and few direction/speed modes; reject access, budget, power/water and equipment violations before simulation.
2. Seed evenly spaced, waiting-area, fan-only/cooler-only and random feasible layouts. Occupancy guides proposals, not ranking.
3. Evaluate complete layouts jointly across fixed weather/arrival scenarios, not summed single/pair scores. Match random inputs while allowing responsive paths.
4. Accept the first feasible improving move: relocate, rotate, change speed/type/size, add or remove a device. Try moves in shuffled order; cache identical layout/scenario/settings evaluations.
5. When stalled, perturb 2–3 devices and repeat local search, preserving the best incumbent even through worse temporary starts. Restart from other seeds. Full physics remains joint.
6. Refine around several winners, retaining coarse alternatives. Stop at a fixed evaluation budget/tolerance; recheck finalists on finer numerics and held-out scenarios/seeds. Parameters unselected.

Use agreed J; if only eta exists, propose J=(sum p_s B_s)/(sum p_s E_s), sum p=1, under resource/cost limits and minimum coverage. Zero-energy baseline is separate. Thresholds/weights remain open; report B,E,cost,coverage. Check equal-budget random search and tiny exhaustive cases. No global guarantee. [Method source](research.md#variable-neighborhood-search).

## Bus-stop installation compatibility

John's question; proposed, not site-validated. For incompatible installation options (i,j), impose z_i+z_j<=1. This permits neither or either, never both. Conflicts are not transitive: B conflicting with A and C does not prohibit A+C. Actual edges need footprint/access/mounting evidence; overlapping jets alone are not exclusions. At an exclusive slot S, sum_{i in S}z_i<=1; resource demands obey budgets/capacity limits, including groups whose pairs individually fit. Adjustable controls obey 0<=x_i<=x_i_max*z_i; shared outlets do not create extra plant capacity.

These linear constraints work with MILP or the convex quadratic screening objective. Additive benefit is not exact airflow physics. Binary pair logic was checked algebraically by this agent; no actual conflict list, solver run or independent/site validation. Next define sites, clearances, capacities and conflicts while retaining the three required bus-shelter devices.

## Safety and overall effectiveness

Report total B alongside eta: high benefit per kWh need not mean enough benefit. Keep a separate justified heat-exposure measure or risk model; discomfort is not a medical risk estimator. Thresholds, duration effects and vulnerable groups require evidence. Do not claim heatstroke prevention from D or temperature reduction alone.

For the later effectiveness extension, compare human benefit/safety/visitor drawbacks, lifecycle financial cost, environmental effects and nonfinancial practicality. Initially show trade-offs and feasibility constraints without arbitrary aggregate weights. Put all monetary energy/water costs in financial cost; physical emissions and water-resource burden belong to environment. Reliability changes delivered conditions, costs and other outcomes rather than adding a fifth score. Minimum benefit or safety requirements remain proposals, not chosen thresholds.

## Multiple outlets and outdoor wind: formulation proposal

Tianyi proposed the temperature advection–diffusion equation in a screenshot shared by John on 2026-11-07:

$$
\frac{\partial T}{\partial t}+\mathbf u\cdot\nabla T=\alpha\nabla^2T+S.
$$

This predicts T given u, not airflow. Specify initial/inlet/outdoor/surface conditions. S has temperature/time units (q'''/(rho*c_p) for volumetric heat). Avoid double-counting inlet cooling as a distributed source. Effective turbulent mixing, moisture transport for evaporation and possible buoyancy coupling need justification; no solver/closure selected.

Outlet i: position r_i, unit direction d_i, area A_i, shape/spread and volume flow Q_i; uniform normal speed U_i=Q_i/A_i. Cooler constraints couple outlet temperatures/moisture and flow/cooling capacity. Duct pressure/heat/leakage losses and auxiliaries affect power; extra outlets create no extra capacity. Ducting changes standalone-device assumptions.

Outdoor wind is a scenario, not a control. Keep one installation across calm and directional/speed scenarios; probabilities and adaptive controls need justification. Independent jets are not exactly additive: pressure, entrainment, turbulence and obstacles interact without visible crossings; opposing jets can redirect/mix. Uniform zones cannot resolve jets. Start with few layouts; retain 3D for height comparisons. Empirical screening and CFD both need validation (boundaries, turbulence, mesh); writing a field symbol does not solve it.

Sources read 2026-11-07: [NASA fluid equations](https://www1.grc.nasa.gov/beginners-guide-to-aeronautics/navier-strokes-equation/) and [NIST local CFD versus uniform zones](https://www.nist.gov/publications/using-cfd-capabilities-contam-30-simulating-airflow-and-contaminant-transport-and). These establish method distinctions, not validated shelter predictions.

### Mean flow and RMS fluctuations

**Accepted — John, 2026-11-07:** mean velocity and RMS fluctuations; prediction/comfort unvalidated. [Evidence](research.md#interacting-jets-and-wind-comfort). Pairwise MILP is superseded as the general solution.

For local velocity w(t), mean m=E[w], deviation w'=w-m and fluctuation RMS sigma (m/s):

$$
 \mathbf w(t)=\mathbf m+\mathbf w'(t),\quad E[\mathbf w']=0,\quad
 \sigma=\sqrt{E[\|\mathbf w'\|^2]}=\sqrt{2k},\qquad
 s_{\rm rms}=\sqrt{\|\mathbf m\|^2+\sigma^2}.
$$

k has units m²/s². Do not add scalar sigma to m. ||m||<=E[||w||]<=s_rms; comfort remains uncalibrated. Walking uses body-relative velocity. Spatial sampling cannot create temporal fluctuations. Zero mean allows weak/strong fluctuations; incoming weighted RMS is not downstream RMS.

Optional ceiling lambda*[||m||²+sigma²-s_max²]_+ is convex in (m,sigma) for lambda>=0, not linear. Control dependence and threshold need justification.

### PDE integration and corrected optimization status

Deferred optional proposal: discretize (A_0+sum z_i A_i)T=b_0+sum z_i b_i under affine prescribed flow, fixed diffusion and linear boundaries. For binary z_i, L_j<=T_j<=U_j, W_ij=z_i*T_j is enforced by L_j*z_i<=W_ij<=U_j*z_i and T_j-U_j*(1-z_i)<=W_ij<=T_j-L_j*(1-z_i). Binary algebra checked; physical/numerical assumptions unvalidated. Nonlinear airflow, RMS and comfort may prevent MILP. Pairwise data omit higher interactions; full configuration lookup is enumeration. No adopted PDE-constrained solver.

### Repeated-area search as a secondary extension

John's 2026-11-08 proposal, unvalidated: repeat a searched stadium cell. m positions/q states give q^m patterns versus q^(mM) independently configured M cells. Evaluate all active devices jointly. Equivalent geometry alone is insufficient: wind, sun, occupancy and boundary behavior must also repeat. Use periodic interfaces/neighbors, not cut-face walls; validate larger blocks/asymmetric scenarios and classify non-equivalent zones. [Evidence](research.md#periodic-and-symmetric-model-reduction).

B_total≈M*B_cell; E_total≈M*E_cell+E_shared (no double counting); efficiency is their ratio. Check whole-site capacity, pressure, costs and budgets. Best repeated pattern is not unrestricted optimum; larger cells can test alternating patterns. Apply neighborhood search to cell patterns if enumeration is too large. No cell size/tolerance adopted.

## Rail-station extension and missing inputs

Behavior, geometry and outdoor exposure are independent inputs: stationary queues can be narrow, circulation broad/bidirectional, and uses can change over time. Model mixed waiting/movement in one benefit framework. Evidence, read 2026-11-06: [Network Rail sections 3.5/3.7](https://www.networkrail.co.uk/wp-content/uploads/2023/12/NR-GN-CIV-100-03-Station-Capacity-Planning-guidance.pdf), [NYC mixed-use plazas](https://www.nyc.gov/html/dot/html/pedestrians/nyc-plaza-program.shtml); neither is cooling-performance evidence.

Sections exchange people/air/heat/moisture and share plant; independent optimization needs justification. Representative paths suffice when adequate; test occupancy redistribution near cooling and retain histories for safety. Avoid double counting. Deep interiors/enclosed refuges cannot replace semi-open venues. Before ranking choose comfort, geometry, weather, occupancy and performance. Fan cooling is perceived; evaporative figures are air-temperature maxima; kW/hr remains unresolved. Original Problem B read through 2026-11-07; AI assisted interpretation/equations/checks/drafting.

## Candidate measures within the four agreed categories

Options, not adopted weights:

- **Human benefit:** matched-baseline comfort, diminishing benefit/overcooling; distinct heat risk; coverage/person-time and vulnerable groups; activity/clothing; noise, drafts, wetting, hygiene, visual intrusion and obstruction. Avoid double counting dissatisfaction; outage timing matters.
- **Financial:** purchase/delivery/installation/utilities/site work; electricity, water/treatment, consumables, staff/cleaning/inspection/repair; replacement/removal/disposal less residual value over a common horizon. Lost space/revenue, closures and backup rental only when relevant. Count each expense once; failure's low bills are not success.
- **Environmental:** operational/embodied emissions, water scarcity, refrigerant leakage, materials/transport/replacement/waste, wastewater, heat discharge and environmental noise. Separate physical burdens from monetary prices; avoid duplicate climate impacts. Failures add resource use.
- **Nonfinancial practicality:** footprint/structure/mounting/utilities/drainage; seating/signs/access/exits; supervision/refill/storage, equipment safety/sanitation; service/recovery/relocation/scaling. Some are feasibility constraints; do not rescore benefit or labor cost.

Reliability is integrated, not a fifth category. Comfort/risk thresholds and priorities remain open. [WHO heat/health](https://www.who.int/news-room/fact-sheets/detail/climate-change-heat-and-health) supports separate vulnerability/risk; [CBE comfort factors](https://cbe-berkeley.gitbook.io/fans-guidebook/practitioner-summary/elevated-air-speed-and-thermal-comfort) needs outdoor applicability checks. Temperature reduction alone does not establish heatstroke prevention.

## Technology and installation options

Unselected options; required bus devices remain fan and two wet-pad coolers. Specify plant capacity/location, outlets/flow/direction, utilities, heat rejection and controls separately. Air distribution creates no extra cooling capacity.

- Fans move air over people; evaporation through wetted media lowers supply temperature and adds humidity. Indirect evaporation separates wet and supply streams. [CBE](https://cbe-berkeley.gitbook.io/fans-guidebook), [UK definitions](https://etl.energysecurity.gov.uk/products/heating-ventilation-air-conditioning-hvac/evaporative-air-coolers).
- Mist needs evaporation, drift/wetting and hygiene control ([Melbourne demonstration](https://research.unimelb.edu.au/strengths/updates/impact/mist-demonstrates-a-context-aware-outdoor-urban-cooling-system)). Refrigeration needs power, condensate drainage and outdoor heat rejection ([PNNL](https://basc.pnnl.gov/resource-guides/air-conditioning)). Radiant panels need a cold source, exposure and condensation control ([UBC prototype](https://sala.ubc.ca/research/the-cold-tube/)).
- Compare overhead, column, seat-area, remote-plant and portable layouts against occupancy, obstacles and wind. Check access, structure, utilities, service, [shade](https://www.epa.gov/heatislands/guide-reducing-heat-islands) and heat recirculation. [Storage](https://betterbuildingssolutioncenter.energy.gov/resources/combined-heat-and-power-technology-fact-sheet-series-thermal-energy-storage) shifts production with losses; savings are not automatic.
- Central air handling uses ducts; chilled water can feed distributed coil/fans; independent units are another architecture. Under-seat ports supply air, not refrigerant. No evidence says most open stadiums use them. [ASHRAE](https://handbook.ashrae.org/handbooks/S20/IP/s20_ch04/s20_ch04_ip.aspx), [NLR](https://hvacresourcemap.nlr.gov/commercial-hvac/all-systems/air-water-distribution/ahu).
- Heat pipes transfer heat to a cooler sink, not create refrigeration ([NASA](https://www.nasa.gov/smallsat-institute/sst-soa/thermal-control/)). Coil precooling/reheating may assist dehumidification ([DOE](https://www.energy.gov/eere/buildings/articles/2014-08-28-issuance-energy-conservation-standards-packaged-terminal-air)); distinguish chilled-water/refrigerant lines.
- Ducted evaporation remains proposed: engineered spray sections need evaporation distance, droplet separation, drainage, treatment and humidity control. Deliver humid air downstream; alternatively pipe water to final mist nozzles. Include duct losses and fan/pump power; standalone ratings do not establish ducted consumption. [Condair](https://www.condair.de/downloads/10-point-guides/10-point-guide-to-specifying-humidifiers-en-rt.pdf), [CAREL](https://www.carelparts.com/amfile/file/download/file/2230/category/2205/); dimensions are equipment-specific.

## Optional duct network and installation model

Discussion recorded 2026-11-07, John / general-chat agent. **Accepted conceptual clarification:** temperatures are stored at nodes; each segment has inlet/outlet temperatures, airflow and heat-transfer properties. John acknowledged this representation. Network optimization and specific loss assumptions remain proposals, not mandatory core features. Algebra/unit checks only; no site calibration, pressure solution or independent validation. Applies to ducted options, not automatically to the problem's standalone devices.

### Construction and routing

Keep existing-duct retrofit and new construction as distinct scenarios. Existing usable ducts have no new construction charge, but modifications/capacity upgrades cost money. Do not assume existing infrastructure without evidence. For a new system, fewer outlets save a shared segment only if no remaining outlet needs it.

Use binary plant y_k, duct b_e and outlet z_i decisions:

$$
C_{\rm install}=\sum_kF_ky_k+\sum_eD_eb_e+\sum_iO_iz_i.
$$

Costs use one currency/horizon and include relevant labor, supports and site access; charge shared segments once. Benefit can be maximized under a cost budget rather than converting comfort into money. A weighted cost penalty is another unselected option; capital cost is distinct from operating/lifecycle costs.

Agent proposal: define feasible corridors and candidate junctions/segments; jointly select network and outlets. Fixed routes are a simpler fallback. Continuous obstacle-avoiding routing is optional harder scope; refinement cannot prove a globally optimal physical layout. For a fixed supply path P_i, z_i<=b_e for each e in P_i. For selectable routes, use root supply, node flow conservation and 0<=f_e<=f_e_max*b_e, with outlet delivery limited by installation. If using a tree, explicitly enforce connected root-to-served-outlet paths, one parent and no cycles; conservation alone does not enforce a tree. Multiple independent plants give a forest. Discrete size choices change segment costs/capacities. Capacity/conservation do not establish adequate fan pressure; check pressure losses and fan electricity separately.

### Node temperatures and accumulated heat gain

Assume steady sensible heat transfer, constant properties, prescribed surrounding temperatures, and sealed insulated ducts; all are proposed simplifications. Define gamma_e=U_e*A_e/(m_dot_e*c_p), alpha_e=exp(-gamma_e). U is W/(m² K), A is duct heat-transfer surface area (perimeter times length), m_dot is kg/s, c_p is J/(kg K); gamma is dimensionless. On a constructed active segment e=(u,v):

$$
T_v=\alpha_eT_u+(1-\alpha_e)T_{a,e}.
$$

At a branch, outgoing ducts initially share the junction temperature, then warm differently. Trunk airflow is the sum of downstream deliveries. For a unique root-to-outlet path and common surrounding temperature:

$$
T_i=T_a+(T_r-T_a)\exp\left(-\sum_{e\in P_i}\gamma_e\right).
$$

Different surrounding temperatures require segment recurrence; no single common-ambient exponential applies. For variable paths, binary path indicators can replace membership in the sum, but decision variables inside the exponential do not automatically preserve convexity/MILP.

Prefer conditional segment equations with precomputed alpha values for fixed flow or discrete duct/insulation/flow modes; linear implications can be encoded with indicators or justified bounded big-M constraints. Modes must conserve shared airflow. Freely variable flow changes alpha; fixed coefficients then become approximations. Avoid merging different-temperature streams in the first tree model; variable-flow mixing introduces additional nonlinearities. The resulting duct constraints can be linear, but utility and other physics still determine the overall optimization class.

Source: [duct evidence](research.md#duct-heat-transfer). Zero gain needs sensitivity justification. Startup, leakage, moisture and pressure detail are optional extensions under the simplicity rule. Checks: alpha=1 preserves temperature; alpha in [0,1] bounds it between inlet/ambient. Illustrative .95,20°C,35°C gives 20.75°C. No coefficients, modes, sizes, routes, budget or tolerance selected.

## Station comparison planning

### Proposed comparison for requirement 2b

Expo's elevated EWL platform is now the selected station case; exact geometry and equipment layout remain unresolved. Under matched weather/occupancy, compare ordinary fans and wet-pad cooling within the current device scope. Preserve significant outdoor exchange, clearance and access; hold shade fixed unless explicitly testing a modification. Earlier refrigerated, distributed-duct and radiant precedents remain background research, not the selected comparison. Enclosed refuges cannot replace the semi-open case. See the [reconstruction plan](#selected-venue-reconstruction-plan).

### How the bus model would need to change

Add spatially varying occupancy/paths, outdoor and relevant train-induced exchange, surges/dwell times and shared plant energy (compressors, fans, pumps, controls). Combine temperature, radiation, humidity and airflow into human outcomes, separating comfort from safety. Distinguish measurements, deployments, prototypes, estimates and proposals. No station ranking follows without geometry, weather, occupancy, performance, prices and a benefit measure.
