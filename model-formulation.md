---
length_reason: Maintains the mathematical definitions, assumptions, sourced physical-model limitations and candidate-search proposal needed for team implementation in one document.
---

# Cooling model formulation under discussion

Updated: 2026-11-07. Status: working structure discussed with John, incorporating Tianyi's temperature-equation proposal and assistant-proposed details. No numerical calibration, rankings, technology selection or implementation. Agreed scope and decisions remain in progress.md.

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

## Safety and overall effectiveness

Report total B alongside eta: high benefit per kWh need not mean enough benefit. Keep a separate justified heat-exposure measure or risk model; discomfort is not a medical risk estimator. Thresholds, duration effects and vulnerable groups require evidence. Do not claim heatstroke prevention from D or temperature reduction alone.

For the later effectiveness extension, compare human benefit/safety/visitor drawbacks, lifecycle financial cost, environmental effects and nonfinancial practicality. Initially show trade-offs and feasibility constraints without arbitrary aggregate weights. Put all monetary energy/water costs in financial cost; physical emissions and water-resource burden belong to environment. Reliability changes delivered conditions, costs and other outcomes rather than adding a fifth score. Minimum benefit or safety requirements remain proposals, not chosen thresholds.

## Multiple outlets and outdoor wind: formulation proposal

Teammate proposal, supplied by the owner as a screenshot on 2026-11-07: use the temperature advection-diffusion equation, dT/dt + u dot grad(T) = alpha Laplacian(T) + S (with the time derivative partial), to represent wind transporting cooled air. This supplies a candidate temperature component of the predictor, not the airflow solution or optimization itself. T varies in space and time; u must be prescribed, measured or computed separately. Constant-alpha form assumes an appropriate simplified transport model; molecular diffusivity alone generally does not represent turbulent mixing, so an effective diffusivity/closure may be needed and justified. S has temperature/time units; volumetric heat input q''' would enter as q'''/(rho c_p). Supply air is normally represented by inlet temperature and airflow boundary conditions; a distributed source is an alternative approximation and must not double count inlet cooling. Initial temperature, open-boundary conditions and shelter-surface heat transfer remain needed. Evaporative cooling additionally requires supply moisture information and moisture transport if local humidity is to be predicted. This is under discussion, not an adopted or validated solver.

Owner asks how arbitrary outlet locations, number, directions and speeds can interact with variable outdoor wind. Do not treat the previously suggested single side-mounted outlet as adopted. Separate the airflow predictor from the optimizer: a proposed installation plus weather produces local velocity, temperature and moisture; occupants sample those conditions; the optimizer compares the resulting benefit/resources.

For outlet i specify position r_i=(x_i,y_i,z_i), unit direction d_i, outlet area A_i, volume flow Q_i, shape/spread and supply temperature/moisture state. For an approximately uniform discharge normal to its area, exit speed U_i=Q_i/A_i; these three quantities are not independent. Supply thermal state is constrained by cooler technology and weather. Use finite feasible mounting positions/directions and optional installation indicators for an initial search. Common-plant outlets share available flow/cooling capacity; duct resistance and extra auxiliaries affect achievable flow and power. Outlet count cannot provide unlimited free capacity. Splitting a cooler into ducts changes the supplied baseline device unless explicitly modeled as an extension.

Represent outdoor wind as scenario inputs, including direction/speed and turbulence assumptions where needed, not controllable design variables. Use calm and multiple wind scenarios, with probabilities only if justified. Evaluate one fixed installation across scenarios; any adjustable settings are constrained by actual control capabilities.

The resulting field has one local velocity vector u(x,y,z,t), plus temperature and moisture. Independent single-outlet velocity solutions generally cannot be added exactly: pressure, entrainment, deflection, turbulence and obstructions cause interaction. Opposing jets do not simply cancel everywhere; they can redirect air and mix. Temperature drops also cannot be added as independent bonuses. Coupled mass/momentum/heat/moisture balances, or validated approximations of them, are needed. A simple well-mixed occupancy zone model cannot by itself resolve local outlet direction.

A few candidate layouts and steady mean-wind scenarios are a proposed first reduction; retain three-dimensional geometry when comparing overhead versus low outlets. A justified empirical jet approximation may screen weakly interacting layouts; strongly interacting jets require more detailed validation or CFD. CFD has its own boundary-condition, turbulence and mesh uncertainties. No solver or empirical spreading/decay coefficients selected. Do not write a black-box predictor symbol as if the physical problem were solved.

Sources read 2026-11-07: [NASA fluid equations overview](https://www1.grc.nasa.gov/beginners-guide-to-aeronautics/navier-strokes-equation/) for coupled velocity/pressure/energy and numerical fluid modeling; [NIST local CFD versus well-mixed zones](https://www.nist.gov/publications/using-cfd-capabilities-contam-30-simulating-airflow-and-contaminant-transport-and) for limitations of uniform-zone representations. These support method distinctions, not a validated bus-shelter prediction.

## Rail-station extension and missing inputs

### Occupant behavior versus physical layout: proposal under discussion

The owner proposes subdividing walking areas and tracking airflow, density and speed, with stationary occupants represented at positions and cooling configurations optimized. The subsequent question challenges whether stationary areas can universally be treated as broad seated spaces and moving areas as narrow one-way passages. No such classification has been adopted.

Recommended distinction: specify behavior (dwelling, walking, queuing/browsing), geometry (width, length, branching, obstacles), and environmental exposure (roof/walls/openings, solar exposure and outdoor exchange) separately. These properties may be associated at a selected venue but do not determine one another. Stationary does not mean seated or assigned a seat; circulation can be broad, bidirectional or crossing. Both groups have entry/exit patterns. A single location can change behavior over time; physical cooling/airflow interactions can cross behavioral-zone boundaries. Fully enclosed spaces can inform boundary comparisons but do not replace the required semi-open case.

Counterexamples to test the proposed simplification include narrow bus shelters or queues with stationary occupants, broad plazas with crossing pedestrians, and covered markets combining browsing, walking, queues and stationary vendors. These are illustrative configurations, not claims about a selected venue. Network Rail's [Station Capacity Planning manual](https://www.networkrail.co.uk/wp-content/uploads/2023/12/NR-GN-CIV-100-03-Station-Capacity-Planning-guidance.pdf), December 2023, sections 3.5 and 3.7, explicitly treats concourse waiting and circulation together and distinguishes one-way and two-way passages. [NYC DOT's plaza program](https://www.nyc.gov/html/dot/html/pedestrians/nyc-plaza-program.shtml) describes pedestrian public spaces with seating, markets and events. Sources read 2026-11-06; evidence of mixed use, not measured cooling performance.

Use distinct occupancy/movement rules within a shared thermal and benefit framework. Separate zone calculations or optimizations are defensible approximations only when relevant people/air transfers and shared plant/budget constraints are negligible or explicitly accounted for. For a first simplified scenario, keep occupancy fixed across cooling alternatives and state this assumption; sensitivity to people gathering near cooling can be considered later. Decide whether individual trajectories are necessary after checking whether zone counts and dwell times capture the comparison. Detailed crowd simulation is not required by the problem.

Replace one served zone with occupied zones connected to each other and outdoors; model airflow/heat/moisture transfer where needed. Zone division alone does not predict performance: a physical or empirically calibrated mapping from equipment, weather, layout and operation to local conditions is still required. Count moving people by zone and time without double counting; individual exposure histories may be needed for safety. Deep mall interiors with little outdoor exchange are weaker primary cases than exposed passages and waiting zones.

Before calculation: select a defensible comfort mapping; specify shelter geometry, weather, occupancy/dwell time and coverage; estimate actual equipment performance and power. The problem's fan reduction is perceived, evaporative reductions are air-temperature changes, all are maxima, and the printed kW/hr energy label remains ambiguous. Treating 0.25, 1.2 and 2.5 as average kW requires an explicit team assumption. No ranking follows directly from dividing the supplied temperature numbers by those power numbers.

Source: 2026_HiMCM_Problem_B.pdf, reread in full 2026-11-06. This file records actual AI assistance: proposed notation, equations, interpretation, limiting-case checks and drafting. It is not evidence of independent team derivation.
