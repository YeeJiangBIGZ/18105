# Model & Framework | HiMCM 2026 Problem B

> Repository: PDE + Agent-based simulation for open/semi-open shelter cooling efficiency evaluation  
> Updated: 2026-11-08  
> Team scope: Requirement 1, 2, 3 core model; MILP optimization reserved for extension / Requirement 4

## Overview

This model evaluates cooling efficiency of **open / semi-open waiting venues** under three given air-conditioning strategies:

- A: Circulation fan
- B: Small evaporative cooler
- C: Large evaporative cooler

> **Important semantic note:**  
> "Air conditioning" in this problem follows its **broad engineering definition (air conditioning of flow, temperature and humidity)**, not the narrow everyday definition of vapor-compression refrigeration. Vapor-compression central air conditioning is economically impractical for largely open shelters with continuous air exchange with ambient, and is only discussed in limitation / future work sections, not in our main simulation.  
> The open freezer analogy in the prompt is adopted for **efficiency evaluation logic only**, not for cooling mechanism comparison.

Our core framework couples a **PDE flow solver** (velocity, temperature, humidity field) with **agent-based pedestrian simulation**. The unified pipeline works for all three devices, with physics source terms adjusted by equipment type.

---

## 1. Definition of Cooling Efficiency (Requirement 1)

### Metric Definition

We define cooling efficiency $\eta$ as the ratio of **total human thermal comfort benefit** over **total energy consumption**:

$$
\eta = \frac{\text{Total Cooling Benefit }(B)}{\text{Total Energy Cost }(E)}
$$

- **Total Benefit $B$**: Integrated reduction of thermal discomfort for all pedestrians over their entire dwelling time inside the venue.  
  Discomfort $D(\theta)$ is a function of **perceived equivalent temperature $\theta$** (apparent temperature / heat index), which combines air temperature $T$, wind speed $u$, and relative humidity $RH$.
- **Total Energy Cost $E$**: Cumulative electric energy consumed by the cooling device during the simulation period.

> **Key distinction:**
> - Evaporative coolers (B, C): Improve comfort both by lowering real air temperature and increasing wind speed.
> - Fan (A): Does **not change air temperature**. Comfort gain comes purely from elevated wind speed, which accelerates skin convective and evaporative heat loss and reduces perceived temperature $\theta$.

---

## 2. PDE Governing Equations & Source Term Setup (Requirement 2 Core Model)

We solve transient advection-diffusion PDEs for scalar fields, plus momentum transport for velocity field.  
General scalar transport form:

$$
\frac{\partial \phi}{\partial t} + \boldsymbol{u} \cdot \nabla \phi = \alpha_\phi \nabla^2 \phi + S_\phi
$$

Where $\phi$ can be temperature $T$, humidity $RH$; $\boldsymbol{u}$ = velocity vector field; $S_\phi$ = source term.

### Case A: Fan Only

- Temperature source: $S_T = 0$. Temperature field is uniform and fixed to ambient $T_{amb}$. Temperature equation becomes trivial and is not solved dynamically.
- Humidity source: $S_{RH} = 0$. Humidity remains ambient.
- Momentum source $S_u \neq 0$: Fan injects momentum to create spatially non-uniform wind field.
- PDE solver focus: Resolve velocity distribution, including wake, obstacle shielding, dead zones and multi-fan interference.
- Perceived temperature $\theta(x,y)$ is calculated post-simulation from $T_{amb}$, local $u(x,y)$ and $RH_{amb}$.

### Case B & C: Evaporative Coolers

- Momentum source $S_u \neq 0$: Cooler outputs directed airflow.
- Temperature source $S_T < 0$ (cooling source): Air is cooled by latent heat of water evaporation.
- Humidity source $S_{RH} > 0$: Evaporation increases air moisture.
- Hard physical constraint: Maximum achievable temperature drop bounded by wet-bulb temperature of ambient air.
- Solve full coupled fields: $\boldsymbol{u}(x,y,t)$, $T(x,y,t)$, $RH(x,y,t)$.

> **Assumption recorded in paper:** Evaporative cooling performance is climate-dependent; efficiency degrades under high ambient humidity.

---

## 3. Agent-Based Pedestrian Model (Coupled with PDE fields)

Pedestrians are independent intelligent agents moving inside the venue:

1. Agents enter at given arrival rate, follow realistic walking trajectories.
2. Agents are utility-driven: they tend to move toward regions with lower discomfort (better perceived cooling), subject to physical boundaries, obstacles and crowd collision constraints.
3. At each timestep, each agent samples local PDE field values ($T, u, RH$) at its coordinate to compute $\theta$ and discomfort $D(\theta)$.
4. Integrate $D(\theta)$ over time for every agent from arrival until departure to accumulate total cooling benefit $B$.

> This captures a critical feedback: people actively seek better cooling zones, which changes the distribution of benefit and the final computed efficiency. Static uniform passenger placement (common in simpler teams’ models) is avoided.

---

## 4. Model Application to Multiple Venues (Requirement 3)

We apply the identical PDE+Agent framework to at least two distinct semi-open waiting venues:

1. Venue 1: Dry-hot climate open bus stop (baseline case from Req 2)
2. Venue 2: Humid climate semi-open railway waiting corridor

For both venues, we compare A/B/C strategies under local ambient climate and geometry.  
Outputs include:

- Spatial contour maps of velocity, temperature, perceived temperature
- Efficiency ranking of A/B/C
- Sensitivity analysis: identify dominant venue characteristics that decide cooling efficiency (humidity, openness ratio, crowd density, shelter geometry)

---

## 5. Model Strengths

1. **Physically consistent first-principle foundation**: PDE resolves airflow and scalar transport, instead of oversimplified empirical distance-decay formulas.
2. **Unified architecture**: One simulation pipeline supports fan and evaporative coolers, only source terms modified.
3. **Captures spatial heterogeneity**: Wind dead zones, shelter blockage, flow interference are naturally captured.
4. **Endogenous pedestrian behavior**: Agents move to chase comfort, which improves realism beyond static passenger grids.
5. **Fair evaluation metric**: All three devices feed into the same $\eta = B/E$ objective, enabling direct comparison.

---

## 6. Limitations & Future Work

1. This model ignores vertical stratification (cold air sinking / buoyancy effect) in the baseline 2D implementation. Vertical 3D extension can be added as an extension for large tiered venues such as stadium stands.
2. We do not model vapor-compression air conditioning in main simulation. Vapor-compression systems are suitable for fully enclosed buildings but thermally and economically inefficient for open/semi-open shelters studied here. It can be added as an extra strategy for future comparison.
3. Turbulence is approximated by diffusion coefficients; high-fidelity LES/NS simulation is computationally too heavy for this competition scope.
4. The agent utility function does not include fine-grained individual physiological variance (age, clothing, metabolic rate).
