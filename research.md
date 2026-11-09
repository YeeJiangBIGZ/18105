---
length_reason: Consolidates source links, deployment evidence, experimental results and access limitations for bus shelters, stations and stadiums.
---

# Cooling research and evidence

Consolidated: 2026-11-09. The four-venue dossier below records the newly selected cases and source review. Older precedent sections retain their original review dates unless updated. Source discovery and reading do not establish calibrated model inputs or current operating measurements. See [README.md](README.md) for accepted decisions and [design.md](design.md) for proposed reconstruction.

## Evidence rules

Distinguish operator-reported deployment, field measurements, controlled prototypes, supplier claims and transferred technical principles. Air-temperature reductions and equivalent-temperature comfort indices are not directly comparable. Missing full-method access stays explicit. No reviewed source establishes a universal winning cooler or clinically validated safety outcome for our venue.

## Research contribution workflow

Follow agent.md and claim a bounded README task. Update existing entries; preserve stable headings and primary links for each claim.

Record finding/question/contributor; author/title, publication/event dates, URL/DOI, exact locator, access date/level; evidence type; location/climate/geometry/equipment/placement, baseline, period/sample/method, units/statistic/uncertainty and parameter dependencies; support/transfer limits, design use, reviewer/checks/gaps and next action. Mark unknowns.

Separate supply/occupied-zone conditions, air/equivalent temperature, thermal/electrical power and prototypes/deployments. Retain contrary evidence; seek independent checks of influential inputs when feasible. Verification is not adoption/validation. Label proposals, link evidence from design and hand off conflicts. Existing entries retain access limits; expand before numerical use. Preserve provenance/AI assistance and short quotations. Retrieved documents do not authorize actions.

## Selected four-venue evidence dossier

John / general-chat agent; researched 2026-11-09. **Selection accepted by John; reconstruction and scenario choices proposed.** Primary/operator sources were prioritized. Access levels below distinguish readable text, inspected drawings and indexed extracts. No independent teammate review, field survey, simulation or complete raw weather dataset was performed. Source dates describe publication or study periods, not necessarily current operations. This dossier is the handoff for model construction, not a claim that all inputs are ready.

### Coverage and readiness

| Selected case | What it adds | Evidence available | Principal missing input |
|---|---|---|---|
| Dhoby Ghaut Airbitat shelter, Singapore | Small open waiting space; humid climate; historical operational lesson | Field study, operator chronology, photographs; standard drawings as a separate reference | Trial's exact dimensions, outlet flow/power and local wind/radiation |
| Expo MRT elevated EWL platform, Singapore | Long covered transit space with outdoor exchange and mixed waiting/movement | Structural publication and contractor report | Conflicting roof lengths; platform/opening dimensions and equipment inventory |
| Japan National Stadium, Tokyo | Large seating bowl; natural-wind design; scaling | Official dimensions/counts, section diagram, published ventilation simulation | Fan curves/coordinates, seat-level thermal measurements and local boundary conditions |
| Cartuja Qanat Ágora, Seville | Semi-open public plaza; contrasting summer humidity; thermal storage precedent | Owner geometry/design conditions; technical paper with instrumentation and sections | Fully inspected technical drawings/data; separation of active plant effects from geometry |

The two Singapore venues deliberately share regional climate while changing geometry and occupancy. Tokyo and Seville broaden climate coverage. Wind exposure must be modeled at each site; a city's prevailing wind alone does not establish a ventilated occupied zone. Four venues are our chosen coverage, not a claim that Problem B explicitly requires four additional sites.

### Dhoby Ghaut Airbitat bus shelter

**Identity and chronology — source B1.** [LTA, “What's the Latest Buzz On Our Bus Stop Shelters?”, 26 April 2024](https://www.lta.gov.sg/content/ltagov/en/who_we_are/statistics_and_publications/Connect/bus-stop-shelters.html), subsection “Airbitat Oasis Smart Bus Stop”; full web text read. The trial was outside Plaza Singapura at Dhoby Ghaut. Its original overhead nozzles were redesigned into seat-attached columns after a year; the trial ended in August 2021 because operations/maintenance costs were high relative to ordinary stops. Treat the original and redesigned installations as separate configurations, not simultaneous features or a currently operating system.

**Measured evidence — source B2.** Velasco and Segovia, [“Effectiveness of equipping bus stop shelters with cooling and filtering systems in a city with tropical climate”](https://www.researchgate.net/publication/373484112_Effectiveness_of_equipping_bus_stop_shelters_with_cooling_and_filtering_systems_in_a_city_with_tropical_climate), DOI [10.1108/SASBE-03-2023-0063](https://doi.org/10.1108/SASBE-03-2023-0063); online August 2023, *Smart and Sustainable Built Environment* 13(5), 1330–1345. Author-upload text read: methods/site description, thermal results and limitations. Five March 2018 evening sessions covered 16:20–19:20. Reported shelter area: **32 m²**. The system combined multistage cooling and filtration; technical drawings/specifications were unavailable, and a commercial UBC1 unit was used as a proxy. The mean air-temperature reduction was about **1°C**. Reported 25th–75th percentiles were **31.2–33.4°C** at the original shelter and **30.9–32.5°C** at Airbitat, with RH **48.0–60.9%** and **52.0–62.3%**, respectively. These are not extreme ranges or paired temperature reductions. Wind and mean radiant temperature were not measured, preventing full comfort validation. Non-simultaneous occupancy counts cannot establish preference. Its one-year dismantling statement must be reconciled with B1's later redesign/end chronology.

**Reconstruction implication (our proposal).** Begin with the documented 2018 configuration because it has corresponding field observations; retain the 2019 redesign as a later placement comparison if its geometry can be established. An area alone does not determine length, depth or roof height. The earlier 9 × 3 m / 27 m² illustration derives from a different LTA standard and must remain a separate conceptual reference, not an as-built Airbitat model. Use photographs for topology and label any inferred dimensions; do not infer installation permission, loading or utilities from appearance.

**Missing before quantitative validation:** trial plan/section and orientation; outlet number, size, velocity, temperature/RH and control schedule; actual electrical/water use; time-aligned ambient and occupied-zone observations; shade/radiant conditions; boarding/waiting distributions. B2 can support an order-of-magnitude temperature check for its historical weather and equipment, not validation of ordinary wet-pad fans. The stop ID/precise coordinates were not verified in this review. See [standard drawings and DataMall access](#candidate-geometry-and-data).

### Expo MRT elevated platform

**Boundary.** Study the elevated East–West Line platform at Expo, not the underground Downtown Line or the neighboring exhibition halls. Keep stairs/escalator openings, roof, platform edges and track-side exchange explicit. Exact current boundaries and screen-door geometry still need a dated plan/photo check.

**Structural source E1.** BCA, [*Structural Steel Design and Construction*](https://www1.bca.gov.sg/docs/default-source/docs-corp-news-and-publications/publications/for-industry/buildability-series/structural_steel_design_and_construction_lowres.pdf), Table 4.1 and Expo case, printed p. 63. Indexed primary-document extracts read; direct PDF retrieval failed, so drawings were not visually verified. The publication gives a platform roof **200 m × 29 m**, **four V-shaped columns**, and a separate ticket-hall roof **38.7 m diameter**. Project dates are July 1998–January 2001. These are roof dimensions, not usable waiting-floor dimensions.

**Conflicting source E2.** [Aveng Annual Report, June 2004](https://www.sharedata.co.za/data/004183/pdfs/aveng_ar_04.pdf), printed p. 38, “Expo station: Singapore”; indexed passage and photograph description read, direct PDF access intermittent. It describes a **130 m** titanium-clad elliptical roof and **40 m** stainless-steel disc. Its “up to four degrees cooler” statement has no measurement protocol in that passage and is not adopted as an air-temperature offset.

**Open discrepancy:** 130 m versus 200 m is consequential. Do not average them, silently choose one, or assume they refer to the same extent. Compare a dimensioned plan with a scaled map and identify which structure/extent each source measures. The rounded disc sizes alone do not resolve the platform-roof discrepancy. No exact reconstructed geometry is adopted.

**Model value and missing inputs (our assessment).** A platform strip can test localized cooling, crosswind loss and crowd pulses without simulating the entire interchange. It needs actual platform width/elevation, roof section, openings, obstructions, boarding zones and feasible mounting areas. No Expo-specific current fan count, manufacturer curve, power, mounting schedule or measured cooling dataset was verified. A fleet-wide fan announcement would not supply those values. Initially compare train-present and train-absent snapshots; train-induced transient airflow is an optional refinement, not something a static outside wind automatically includes. Station entry counts would need conversion into platform-specific person-time, with uncertainty.

### Japan National Stadium

**Official inventory — source J1.** Japan Sport Council, [facility overview](https://www.jpnsport.go.jp/kokuritu/Default.aspx?TabId=439), “heat measures” and facility summary; full text read, no publication date shown. Reported dimensions are approximately **350 m north–south × 260 m east–west**, height **47 m**; three seating tiers and **67,750 seats**. Heat measures include **185 airflow fans**, mist at eight locations and separate conditioned rest rooms. Capacity is not attendance; 185 is an installed inventory, not a universal stadium maximum or a count of evaporative coolers.

**Section and mechanism — source J2.** JSC, [*Overview of the Japan National Stadium*](https://www.jpnsport.go.jp/corp/Portals/0/kokuritsu/overview_of_the_JapanNationalStadium.pdf), PDF p. 6, section D. PDF downloaded; text and rendered page inspected. Eaves and terraces admit natural wind; the drawing depicts heat/moisture leaving above the field and supplementary fans around the lower two tiers. Fan-position diagrams are explicitly illustrative, not exact installation coordinates. This is design intent, not measured airflow under all weather.

**Simulation precedent — source J3.** [Kyushu University research release, June 2021](https://www.kyushu-u.ac.jp/ja/researches/view/604), results/publication details; web text read. It reports Uchida and Araya's [2021 stadium LES study, DOI 10.1155/2021/8822548](https://doi.org/10.1155/2021/8822548), using a GIS-based three-dimensional model. For a roughly **3 m/s northerly wind above the stadium**, the simulated initial fluid layer largely dispersed in about **20 minutes**. This is one simulated ventilation case, not a measured air-change rate, thermal-comfort result or guarantee for other winds. Full computational inputs and a reusable mesh were not obtained here.

**Reconstruction implication (our proposal).** Use a coarse bowl/opening model to establish different sector exposures, then one or several occupied seating sectors for detailed equipment evaluation. Preserve roof shade, tier slope, rear/concourse openings and local fan direction. Rotational symmetry of seating does not imply symmetry of wind or sunlight. A repeated cell must exchange air/heat consistently with its neighbors; it cannot be independently tiled while retaining one favorable inflow everywhere.

**Missing:** detailed fan positions, operating modes, flow/power/noise curves; tier sections and opening porosity; roof/seat thermal properties; measured local weather and thermal conditions; actual crowd distributions/event duration. Do not assign whole-stadium energy to a small sector or scale a sector's benefit to every seat without exposure/occupancy weights. Mist and rest rooms stay outside the current fan/wet-pad comparison unless explicitly included and costed.

### Cartuja Qanat Agora

**Selected space — source Q1.** [Cartuja Qanat official project page](https://cartujaqanat.com/), “Ágora” and climate-control sections; full text read, page undated. The Ágora is a **750 m² rectangular space**, **2 m below avenue level**, with semitransparent barriers. It is separate from the adjacent amphitheater; that space's capacity must not be transferred. Listed design conditions include air **27°C**, cover **24°C**, outside exchange of **9 h⁻¹ at 37°C** and **7 h⁻¹ precooled to 28°C**, and supply of **21 h⁻¹ at 25°C** through buried ducts and **11 h⁻¹ at 24°C** through submerged ducts. These are project descriptions/design values, not verified simultaneous measurements. Confirm reference volume and operating modes before combining rates.

**Technical source Q2.** Montero-Gutiérrez et al., [“Exploring a new approach to ancient Qanat techniques using earth-air and water-air heat exchangers for efficient natural cooling”](https://doi.org/10.1016/j.enconman.2025.120066), *Energy Conversion and Management* 341 (1 October 2025), 120066; [institutional PDF](https://rodin.uca.es/bitstream/handle/10498/38706/OA_2025_0659.pdf?sequence=1). Indexed primary text/figure captions and publisher summary read; full PDF download was incomplete and failed validation. Figure 2 describes sections of the approximately **20 m × 40 m**, southwest-oriented space; those rounded dimensions do not replace the reported 750 m². Figure 7 locates temperature/humidity sensors along buried/submerged paths and soil/water sensors. Experiments distinguish inactive operation, daytime cooling and nighttime regeneration. Publisher highlights report an 8°C reduction and about 20 kWh of daytime cooling; these are system results, not a uniform occupant temperature reduction or electrical consumption. Raw time series and full methods remain unverified.

**Reconstruction implication (our proposal).** This adds a public plaza rather than another transport facility or stadium. Preserve its sunken geometry, roof, barriers and access openings. First evaluate hypothetical fan/wet-pad alternatives with existing active cooling disabled and shade retained. A separate actual-system study would need ground/water storage, night regeneration, pumps and roof heat exchange. Do not attribute the real hybrid system's performance to a portable wet-pad unit, or give a cooled roof a free benefit in the baseline.

**Missing:** fully inspected dimensioned section and height datum; barrier/opening details; reconciled operating modes and airflows; electrical and water records; occupied-zone velocity/radiation; attendance/dwell patterns; raw experimental data and uncertainties. A 3 m roof-height statement in indexed text needs its reference level checked before use. No claim is made that the original site's active plant fits our simple device scope without modification.

### Weather sources and scenario construction

These are data routes, not a downloaded/cleaned dataset. All were reviewed/discovered on 2026-11-09. Record observation station, coordinates, measurement height, time zone, period, units and missing-data flags when acquiring values; station wind is a boundary reference, not person-level airflow.

| Source / locator / access | What is usable | Limitation / next action |
|---|---|---|
| [Meteorological Service Singapore, Climate of Singapore](https://www.weather.gov.sg/climate-climate-of-singapore), humidity/wind sections; web text | Regional humidity cycle and monsoon context; mean annual RH about 82% | Annual RH is not a hot-afternoon condition or site observation |
| [NEA/data.gov.sg weather collection](https://data.gov.sg/collections/1459/view), collection catalogue; [official API documentation](https://developers.data.gov.sg/); catalogue/docs read | Temperature, RH, wind speed/direction, with some one-minute observations and historical coverage | Download a common interval; verify variable availability and units for each station, not merely the nearest name |
| [JMA normals](https://www.data.jma.go.jp/stats/data/en/normal/normal.html), Tokyo, 1991–2020; published table | July/August mean RH 76%/74%; mean temperature 25.7/26.9°C | Monthly means are context, not an extreme-heat episode |
| [JMA historical observations/download](https://www.data.jma.go.jp/risk/obsdl/), official data route located | Hourly/daily Tokyo forcing and quality flags | Select contemporaneous temperature, humidity, wind and solar data; check station metadata/relocations before transfer |
| [AEMET Seville Airport normals, station 5783](https://www.aemet.es/es/serviciosclimaticos/datosclimatologicos/valoresclimatologicos?k=&l=5783), 1981–2010 table | July mean RH 44%, mean daily maximum 36.0°C; August 48%, 35.5°C | Different normal period from JMA; airport exposure differs from the sunken plaza |
| [AEMET OpenData](https://opendata.aemet.es/), official access route located | Historical/observational weather access | API key/access setup may be needed; no account/key created and no series acquired |

**Proposed sampling:** choose actual simultaneous hot-period records, including hot-calm and humid-hot episodes plus contrasting wind directions when represented. Retain temperature–humidity–wind covariance rather than constructing every combination of independent extremes. Use multiple weather snapshots with duration weights; preserve thermal history if modeling Qanat storage. A controlled same-weather cross-site experiment can separately isolate geometry effects, but label it hypothetical rather than local climatology. Include solar/radiant forcing and distinguish outdoor meteorological direction (“from”) from the simulation velocity vector (“toward”).

### Shared input ledger and next handoff

For every adopted value record `venue/version; parameter; value/range; unit; source+locator; measured/design/proxy/estimated; date/time; reference height or area; uncertainty; intended use`. Keep the actual-system description separate from the hypothetical equipment table. No current source supplies a complete fan curve, water consumption, price, noise and geometry package for all four venues.

1. **First bus case:** establish the historical geometry and a matched weather/occupancy scenario. If dimensions remain estimated, publish them and a sensitivity range; do not label the earlier concept a measured reconstruction.
2. **Equipment inputs:** use the problem's three required device classes, resolve the printed power units, and obtain internally consistent airflow/outlet area/power/wet-bulb effectiveness data. Manufacturer maxima are not uniform occupied-zone performance.
3. **Expo:** reconcile the two roof lengths before scaling a whole-platform model; a labeled generic strip can support early method development meanwhile.
4. **Tokyo:** establish at least windward/leeward sector conditions before repeating a layout. J3 can guide a wind scenario, not validate our comfort calculation.
5. **Seville:** obtain the complete Q2 paper/sections and choose whether real active systems are off or explicitly modeled; budget all associated energy/water consistently.
6. **All sites:** acquire representative occupancy/dwell information and costs. Distinguish capital, maintenance and electricity; use dated local tariffs/currency for later calculations. Actual costs, carbon factors, noise and water rates were not verified in this review. Report scenario rankings with uncertainty rather than inventing a measured winner.

Research status: selection and evidence dossier complete; numerical parameter adoption and physical validation remain open. No authors/operators were contacted, no simulation was run, and no incomplete PDF or third-party drawing was added to GitHub. AI assisted source discovery, comparison and drafting.

## Santa 2025 packing methods and cooling-layout transfer

Reviewed 2026-11-09, John / general-chat agent. Author writeups read through indexed text; direct Kaggle opens had no readable lines. Overview and winner's repository read. No code run or cooling validation.

- [Official task](https://www.kaggle.com/competitions/santa-2025/overview): position/rotate 1–200 non-overlapping trees in small squares; metric sums normalized square areas. Geometric packing differs from cooling coverage.
- [Jeroen Cottaar, first place, 8 Feb 2026](https://www.kaggle.com/competitions/santa-2025/writeups/1st-place-genetic-algorithm-and-gpu-relaxation), key aspects/relaxation: genetic search, GPU relaxation, 180-degree symmetry for even counts and tessellated seeds with edge adjustments. [Author repository](https://github.com/jcottaar/packing) confirms winning solution. Geometric overlap lookup does not establish additive airflow.
- [KiRaRe, second place, 10 Feb 2026](https://www.kaggle.com/competitions/santa-2025/writeups/2nd-place-simulated-annealing-iterated-local-sea), key points/initialization/SA: periodic seeds, multi-object changes, annealing within iterated local/beam search. Search precedent, not cooling-performance evidence.

**Proposed transfer:** construct from empty or a repeated cell; vary fan location, angle, mode, type and count. Annealing can accept worse moves while retaining best feasible output. Evaluate joint cooling, not non-overlapping rigid cooling footprints. Individual maps may suggest moves, not certify combined benefit. Repetition needs wind/sun/occupancy/boundary checks and shared-resource accounting. PDE calls may cost much more than geometry checks. Fixed evaluation budgets bound work, not global optimality; no polynomial exact-optimum guarantee or adoption. Compare with bounded greedy search before choosing an extension.

## Interacting jets and wind comfort

John / general-chat agent, 2026-11-07. Question: can isolated outlet vectors be combined simply while capturing opposing-flow turbulence and maintaining tractable optimization? Primary-source review and algebra only; no shelter measurements, calibrated closure, simulation or independent reviewer. John retained [mean flow/RMS](design.md#mean-flow-and-rms-fluctuations); later corrections supersede pairwise MILP as a general arbitrary-outlet solution. [Direct PDE integration](design.md#pde-integration-and-corrected-optimization-status) is proposed; no physical/optimization model validated.

| Primary source / locator / access | Bounded finding and applicability |
|---|---|
| Koskela et al., *Turbulence correction for thermal comfort calculation*, Building and Environment 36 (2001), 247–255, DOI 10.1016/S0360-1323(00)00002-0. [Full PDF](https://www.aivc.org/sites/default/files/airbase_13388.pdf), §§2.1–2.2, 3.3, discussion; PDF retrieved locally, web renderer later returned 404. [Publisher abstract](https://www.sciencedirect.com/science/article/abs/pii/S0360132300000020). | Distinguishes mean scalar airspeed from magnitude of mean velocity. Laboratory/theoretical correction estimates comfort-oriented speed statistics from directional data. Isotropic fluctuation assumptions underlie the fit; not universal. It needs fluctuation information and does not predict interacting jets from isolated vectors. |
| Stan, *Fundamental Characteristics of Turbulent Opposed Impinging Jets*, Waterloo thesis (2000), [repository abstract](https://uwspace.uwaterloo.ca/items/d58cbacf-1e96-4015-a795-23119d68fa94). Abstract only. | Unconfined opposed round jets, seven configurations spanning L/d=5,10,20 and Re=1500,4500,7500,11000; laser measurements and three k–epsilon models. Geometry/Re changed interaction; mean velocity agreement did not imply accurate turbulence. No universal collision multiplier or shelter calibration. |
| Liu et al., *Influence of nozzle spacing on mixing behavior of two parallel jets from rectangular nozzles*, CIESC 68 (2017), 3708–3716, [original abstract](https://hgxb.cip.com.cn/EN/10.11949/j.issn.0438-1157.20170380). | PIV with varying speed/spacing: spacing delayed merging and altered combined maximum velocity. Same-direction streams cannot generally be replaced by a geometry-free sum. Full-method transfer unverified. |
| Weiss, Coenen and Sánchez, *Aerodynamics of planar counterflowing jets*, JFM 821 (2017), 1–30, [author preprint record uploaded 2022](https://arxiv.org/abs/2202.06579), abstract. | Laminar slot-jet analysis depends on spacing/width, inlet profiles and momentum-flux ratio; general rotational solutions require numerical integration. Not turbulent-person comfort evidence. Avoid mistaking upload date for publication date. |
| Fanger et al., *Air turbulence and sensation of draught*, Energy and Buildings 12 (1988), 21–39, DOI 10.1016/0378-7788(88)90053-9, [DTU original abstract](https://orbit.dtu.dk/en/publications/air-turbulence-and-sensation-of-draught/). Full PDF access failed. | 50 sedentary, thermally neutral subjects at 23°C; speeds 0.05–0.40 m/s, low/medium/high turbulence. Turbulence changed unwanted-draft sensation. Does not justify an identical penalty in hot outdoor conditions. |
| Yu et al., *Impact of wind turbulence on thermal perception in the urban microclimate*, JWEIA 216 (2021), 104714, DOI 10.1016/j.jweia.2021.104714. [Accepted manuscript](https://ira.lib.polyu.edu.hk/bitstream/10397/102800/1/Niu_Impact_Wind_Turbulence.pdf), §2/Fig.1/Table2 and abstract. | 20 young adults; wind-tunnel standing/cycling, 1.5/2.8 m/s, approx. 17/35% turbulence, 25.9–28.7°C and 49–62% RH. Increased turbulence enhanced cooling under tested conditions. Evidence against universally treating turbulence as harmful; no heat-wave or vulnerable-population safety extrapolation. |

**Synthesis/inference:** A local mean vector cannot describe random air motion. Opposed flows may redirect and fluctuate; a mean stagnation point does not imply still air over the whole body, nor guarantee large fluctuations there. Input kinetic energy does not specify how much becomes local turbulence versus organized outflow or dissipation. Equal incoming RMS does not establish equal thermal sensation. Body blockage and movement further change exposure.

**Mathematical checks, not new empirical laws:** for actual velocity w, E||w||²=||Ew||²+E||w-Ew||². Thus a vector plus fluctuation energy can represent a zero-mean/nonzero-RMS state. Input-weighted RMS is instead direction-blind; splitting one stream with conserved weights leaves it unchanged, but that property cannot validate it as downstream speed. Multiplying a resultant by a finite factor leaves exact cancellation unchanged; assigning its direction to a finite RMS is undefined at cancellation and unstable nearby. No reviewed source supplies a universal algebraic merge function of isolated source vectors alone.

**Deferred PDE branch:** binary-product linearization does not validate joint physics. Full-table enumeration and pairwise truncation are not general solutions; direct PDE-constrained optimization remains optional/unvalidated. See design for conditions.

## Variable neighborhood search

Reviewed 2026-11-09: Mladenović and Hansen, *Variable Neighborhood Search*, Computers & Operations Research 24 (1997), 1097–1100, [original paper](https://sci2s.ugr.es/sites/default/files/files/Teaching/GraduatesCourses/Metaheuristicas/Bibliography/HansenVNS.pdf), §2, full text. Changing perturbation neighborhoods followed by local search and incumbent improvement provides a simple non-MILP heuristic. Routing results do not validate cooling. Fan moves/restarts/scenario checks are unvalidated adaptations; no runtime/global guarantee.

## Periodic and symmetric model reduction

Reviewed 2026-11-08, John / general-chat agent. [ANSYS Fluent boundary conditions](https://ansyshelp.ansys.com/public/Views/Secured/corp/v252/en/flu_ug/flu_ug_bcs_sec_bound_cond.html), §§8.4.17–18, full passages read: mirror/periodic reduction requires corresponding flow/thermal patterns as well as geometry. Symmetric geometry can have asymmetric flow; periodic faces connect neighboring cells, while symmetry disallows normal flux. Supports conditional repeated-area modeling, not stadium validation. Site wind/sun/occupancy and shared-resource effects remain untested.

## Occupant obstruction and thermal plumes

Contributor: John / this agent; reviewed 2026-11-07. Question: can point occupants be treated as passive recipients without changing the shelter airflow? Evidence reviewed at abstract level; no outdoor validation, independent reviewer or shelter sensitivity calculation completed. Model simplification remains proposed.

**Cheng and Lin, Experimental investigation into the interaction between the human body and room airflow and its effect on thermal comfort under stratum ventilation**, Indoor Air 26, 274–285; first online 10 April 2015. [Publisher abstract](https://onlinelibrary.wiley.com/doi/abs/10.1111/ina.12208). Heated/unheated simplified manikins and human tests in two rows: local blockage, flow passing over bodies, and changes to downstream flow/temperature with body heating and ventilation rate. Supports separating obstruction from heat-driven flow. Indoor stratum-ventilation conditions do not establish an outdoor negligible-effect threshold; no full-method verification or direct numerical transfer.

**Ma et al., What dominates personal exposure? Ambient airflow pattern or local human thermal plume**, Building and Environment 196 (June 2021), 107790. [University abstract](https://vbn.aau.dk/en/publications/what-dominates-personal-exposure-ambient-airflow-pattern-or-local/), DOI 10.1016/j.buildenv.2021.107790. CFD of one standing person beneath a downward supply opening found regimes dependent on supply speed, opening and height. Reported transition speeds are geometry-specific, not universal bus-stop cutoffs. Supports checking buoyancy when imposed airflow is weak; does not quantify our shelter's performance error.

**Model implication (inference, not adopted):** A point for occupancy/utility and a simplified obstacle for airflow are compatible representations. Start with passive point recipients if justified for screening, then compare the same layouts/weather/occupancy with bodies represented by coarse blocks/cylinders, adding sensible body heat in a further comparison where buoyancy matters. This distinguishes geometric blockage from thermal effects without detailed anatomy. Include low/high occupancy and people aligned downstream of an outlet. Broad sparse flows are a more plausible neglect case than narrow jets or queues directly shielding one another; this is a hypothesis to test, not a density cutoff.

Compare occupied-zone speeds, temperature/moisture, total benefit and configuration ranking, plus poorly served groups. Define an acceptable modeling tolerance before selecting a winner; no numerical tolerance is chosen. Retain obstruction/heat effects if they change the decision or materially understate adverse exposure. If differences are immaterial under representative and adverse scenarios, document the tested range for the simplified model. No claim that effects are negligible is supported yet. When explicitly modeling a solid body, sample surrounding exposure or use a suitable body heat-transfer model; do not use zero no-slip wall velocity as the ambient comfort input.

## Bus shelters

### Candidate geometry and data

John / general-chat agent, reviewed 2026-11-07; status updated 2026-11-09. The LTA-standard reference below was an earlier proposal. Dhoby Ghaut Airbitat is now selected; these standard dimensions are not its surveyed geometry. See the [selected shelter dossier](#dhoby-ghaut-airbitat-bus-shelter). Problem 2a names no city/dimensions; requirement 3 allows data or justified estimates. Preserve outdoor exchange and the required devices.

[LTA September 2025 drawings](https://www.lta.gov.sg/content/dam/ltagov/industry_innovations/industry_matters/development_construction_resources/Street_Work_Proposals/Standards_and_Specifications/SDRE/SDRE14-11_BUS_1-5_September_2025.pdf), rendered PDF page 6/BUS5 rev C: plan depth 3000 mm, size table includes 9 m length, seats/screens/columns/path connections/kerb/bollards/information panels/conduits. Hence proposed 9x3 m footprint; remaining heights/structure need verification. Page 5/BUS4 rev D is separately marked TEMPORARY USE ONLY; do not merge its dimensions into BUS5. Official standard, not surveyed site or approved retrofit; conduits do not establish spare electrical capacity, water or roof loading. No structural/independent review.

[LTA DataMall](https://datamall.lta.gov.sg/content/datamall/en/dynamic-data.html): catalogue checked for stops, arrivals, services and passenger-volume datasets. No credentials, downloads or matched stop; boarding totals are not instantaneous occupancy/paths. [NEA weather collection](https://data.gov.sg/collections/1459/view): temperature/RH/wind, some up to one-minute intervals; no downloaded series or local shelter/radiant correction. Phoenix's Dzyuban study below offers measured thermal conditions, photographs and historical daily ridership 29–107 for six north-facing shelters (summer 2018); not simultaneous occupancy or complete mounting plans. Do not transplant its effects into Singapore.

Candidate mounting regions beneath beams, beside posts, rear seats and an external plant pad remain proposals. Exclude boarding/access paths, sightlines and service clearances; check loading, utilities, drainage and maintenance before declaring feasibility.

Requested inline 3D concept built 2026-11-07: rotatable/top/front/end views, removable roof, bare/fan/ducted alternatives. Assumptions: 9x3 m footprint, 2.7 m roof, two 2.8 m benches, 1.5 m rear opening, 0.8x0.8x1.1 m external cooler, outlet x=1.5/4.5/7.5 m, illustrative posts/screens/ducts. Controls checked in headless Chrome; desktop/narrow renders inspected. Arrows are axes, not solved flow; no CFD or optimization. Inline source remains in chat. Now reconstruct the selected historical trial separately and verify dimensions/feasible regions; no specific geometry or placement adopted.

### Evidence

#### Shade: operating bus stops, field measurements and surveys

Dzyuban et al., published online 2021, International Journal of Biometeorology 66 (2022), 345–356. Phoenix bus-stop fieldwork in summer 2018. Average shaded-versus-sun PET reduction was 19°C. PET is physiological equivalent temperature, not air temperature. Effects varied by time and design; shade did not guarantee comfort. This supports treating sun/shade and radiant heat explicitly, not transferring a constant 19°C adjustment to our shelter.

Source, full PDF accessible: https://link.springer.com/content/pdf/10.1007/s00484-021-02074-4.pdf

#### Fans: comfort mechanism and unfavorable operator experience

CBE explains how air movement can improve thermal comfort without reducing ambient air temperature. Its indoor reference calculations are not automatically bus-stop calibrations.

Source: https://cbe-berkeley.gitbook.io/fans-guidebook/practitioner-summary/elevated-air-speed-and-thermal-comfort

Singapore Ministry of Transport, 7 May 2026: earlier exposed-bus-stop fan trials had unfavorable commuter feedback; no solar-powered fan rollout planned. It also reports limited ambient-temperature impact, which by itself is not a valid test of fan comfort benefit. Trial layout, weather, speeds and measured comfort data are not disclosed in this statement. No universal fan failure conclusion follows.

Source: https://www.mot.gov.sg/news-resources/newsroom/commuter-comfort-at-bus-stops/

#### Evaporative cooling: climate dependence and prototype field evidence

PNNL Building America guidance explains that direct evaporative coolers lower air temperature and add humidity; effectiveness depends on wet-bulb depression, air velocity through media and media condition. It is residential guidance: use mechanism/equation, not residential savings or sizing as open-shelter evidence. Supply temperature can be represented as T_supply=T_dry-epsilon*(T_dry-T_wet); conditions at passengers additionally depend on distribution and mixing. This component effectiveness differs from our human-benefit-per-kWh index.

Source: https://basc.pnnl.gov/resource-guides/evaporative-cooling-systems?existing_homes=602

Guangzhou prototype bus-stop mist study: field measurements and 335 valid questionnaires; indexed publisher abstract reports side spray outperformed top spray and up to 3.1°C air-temperature reduction. Humidity increased. Evidence supports potential benefit even in the tested hot-humid conditions, not universal humid-weather suitability. Mist spray is not the same apparatus as Problem B's wet-pad cooler. Maximum reduction cannot be assumed uniform across space/time.

Source: https://www.sciencedirect.com/science/article/abs/pii/S0378778825015646
Access limit: indexed primary abstract/conclusion available; direct full-page requests returned 403. Do not transfer exact settings, power, water use or reported comfort thresholds without full-method verification.

#### Targeted cooled-air delivery: actual operational lesson

The selected [Dhoby Ghaut dossier](#dhoby-ghaut-airbitat-bus-shelter), sources B1/B2, consolidates the operator chronology and field study. Keep placement/lifecycle lessons distinct from a measured energy-efficiency ranking.

#### Cooled radiant surfaces: experimental alternative

2023 proof-of-concept study of radiant bus-shelter modules in controlled conditions representing hot dry outdoor weather. The abstract reports useful comfort-index improvements. This is prototype evidence, not established large-scale operating performance or evidence that it beats the three assigned devices. No electrical savings or clinical health protection inferred.

Source: https://www.sciencedirect.com/science/article/pii/S0196890423009731
DOI: 10.1016/j.enconman.2023.117627
Access limit: indexed primary abstract read; direct publisher and university repository requests returned 403.

#### Air-conditioned shelter sections: deployed, different boundary

Dubai RTA April 2026 release describes designated air-conditioned sections at main stops alongside shaded outdoor areas. It establishes deployment, not comparative comfort per kWh. An enclosed cooled waiting room is a useful alternative-boundary comparison, not a replacement for the required open-sided shelter.

Source: https://www.rta.ae/wps/portal/rta/ae/home/news-and-media/all-news/NewsDetails/completion-of-726-shelters-for-public-bus-riders

## Duct heat transfer

Reviewed 2026-11-07, John / general-chat agent. [EnergyPlus 26.2 engineering reference](https://energyplus.readthedocs.io/en/v26.2.0/guides/engineering-reference/13.1-airflownetwork-model.html), Node Temperature Calculations, equations 13.61–13.65, full passage read: steady segment outlet temperature is T_out=T_a+(T_in-T_a)*exp[-UA/(m_dot*c_p)]. A is perimeter times length, not cross-sectional area. Node temperatures form a linear system at given flows; this does not establish linearity when flow, geometry or mixing weights vary. Source describes a simplified distribution model, not validated outdoor stadium performance. [DOE duct guidance](https://bsesc.energy.gov/energy-basics/hvac-sealed-and-insulated-metal-ducts), What/Why, full page read: insulation limits heat transfer and sealing limits leakage; neither proves zero loss. No shelter coefficients or loss percentages obtained. Intended use: [optional duct model](design.md#optional-duct-network-and-installation-model). Check common-ambient path derivation and network flow consistency; test loss sensitivity before omitting it. No independent review or site validation.

## Stations and related technologies

### Evidence from public transport facilities

#### Chai Wan station in Hong Kong: localized cooling in an open station

Eastern District Council minutes of 21 June 2022, printed page 6, paragraph 13, record an MTR representative explaining that the station used an open natural-ventilation design. Fans and spot coolers had been provided at the concourse and platform. Full air conditioning faced electrical-capacity and plant-space constraints. This establishes an actual deployment of spot cooling in a directly relevant setting, but supplies no equipment capacities, energy totals, comfort measurements or current operational status.

Source: [official meeting minutes](https://www.districtcouncils.gov.hk/east/doc/2020_2023/en/committee_meetings_minutes/ttc/ttc_14th_minutes_20220621_en.pdf).

#### Tokyo subway: two documented mechanical architectures

Tokyo Metropolitan Government engineers describe centralized cooling through ceiling outlets using air-handling units (AHUs), and local cooling through fan-coil units (FCUs) or packaged air conditioners (PACs). FCUs can share chilled-water infrastructure; PACs have different water-cooled or air-cooled configurations. Local units recirculate nearby air and create uneven cooling zones. These examples concern underground stations: equipment principles are transferable, but their performance cannot be assumed for an outdoor-exposed waiting area.

Source: [Tokyo TECH, 3 February 2023](https://note.com/tokyo_tech/n/n69eab31f6f18), sections 3(1) and 3(2). Do not repeat its simplified terminology treating water as a refrigeration-cycle refrigerant: chilled water is a heat-transfer medium in the distribution loop.

#### Singapore: ventilation and hybrid cooling

LTA's above-ground station account identifies natural ventilation, greenery and HVLS fans as approaches; Canberra is a named naturally ventilated example. LTA's 2023/24 sustainability report, printed page 24, documents fans combined with air conditioning at TEL4 stations, including a photograph of Katong Park. This is evidence that controlled air movement is part of actual station practice. TEL4 is an underground comparison, not automatically a semi-open case.

Sources: [LTA above-ground stations](https://www.lta.gov.sg/content/ltagov/en/who_we_are/statistics_and_publications/Connect/greenmrtstations.html); [LTA sustainability report](https://www.lta.gov.sg/content/dam/ltagov/who_we_are/statistics_and_publications/report/pdf/LTA_SR2324.pdf).

The owner's earlier strong-draft concern remains relevant to comfort, while the current fan/cooling-fan scope supersedes the stadium fan exclusion. Do not turn discomfort in some conditions into a general physical claim that all air movement harms comfort. A draft penalty or acceptable airflow constraint is a proposal, not a selected numerical limit.

#### Futamatagawa station in Japan: mist experiment

A primary conference-paper record reports a summer-2007 experiment with 30 dry-mist nozzles in two stair zones connecting platform and concourse. Reported mean air-temperature differences were 1.63 K from 09:00–13:00 and 1.9 K from 13:00–15:00 under the tested intermittent operation. These are local trial results, not a guaranteed reduction, energy saving or present-day installation claim. Humidity, wind, control conditions and wetting must be considered.

Source: [Ishii and colleagues, conference paper](https://researchmap.jp/yoonlab/published_papers/21864534/attachment_file.pdf). Access limitation: primary indexed text and section 4 were available through search; direct PDF retrieval returned 403. Full numerical extraction and survey sample validation remain necessary before adopting its quantitative results. No unrelated secondary review is being used as proof.

#### Yokohama: separate cooled waiting rooms

The city's station-cooling page, updated 28 August 2023, explicitly distinguishes platform cooling from air-conditioned waiting places. This supports enclosed refuge rooms as an actual strategy, not as cooling of the whole semi-open environment. If considered, include their capacity, accessibility, occupancy and the people left outside.

Source: [Yokohama City Transportation Bureau](https://www.city.yokohama.lg.jp/kotsu/sub/norikata/ekireibo.html).

### Additional technologies and scope boundaries

#### Outdoor radiant cooling: direct experimental evidence

PolyU researchers tested a prototype with two wall panels and one ceiling panel, supplied by a water chiller. A companion comfort study involved 248 participants outdoors. The abstracts report improved thermal sensation under tested conditions and identify panel temperature, weather and condensation as important. This is a research prototype, not evidence of normal railway deployment or proven heatstroke prevention.

Sources: [thermal performance and energy efficacy, 2024](https://research.polyu.edu.hk/en/publications/thermal-performance-and-energy-efficacy-of-membrane-assisted-radi/), DOI 10.1016/j.scs.2024.105787; [comfort study, 2024](https://research.polyu.edu.hk/en/publications/thermal-comfort-investigation-of-membrane-assisted-radiant-coolin/), DOI 10.1016/j.scs.2024.105634.

Only abstracts and publisher section excerpts were reviewed. Do not interpret the thermal heat-extraction figure in watts as measured whole-system electrical power or copy a thermal-sensation result as a health-safety threshold.

#### Suvarnabhumi airport: radiant floor plus displacement ventilation

Supplier Uponor documents floor cooling combined with displacement air supply in the terminal/concourses, with active dehumidification and solar protection. This is a useful large-space technology example, but its controlled indoor humidity makes it an inappropriate direct demonstration of performance in an open-air terminal. The documented pipe-water temperatures are not universal design recommendations.

Source: [Uponor project account](https://www.uponor.com/en-en/r/bangkok-airport), completed 2006.

#### Reducing air exchange is a supporting design intervention

MTR describes platform screen doors as reducing air displacement caused by trains. This supports considering the paths by which cooling is lost. Full-height separation, partial barriers and a fully enclosed room are materially different boundaries. Do not assume a safety barrier seals air exchange, or that closing every opening preserves the required semi-open scenario.

Source: [MTR emissions and station measures](https://www.mtr.com.hk/sustainability/en/greenhouse-gas-emissions-reduction.html). Its description is mechanism evidence, not a numerical energy-saving estimate for our venue.

#### Evaporative coolers and heat pipes

The problem itself requires pad-based evaporative coolers in 2a. They remain candidates for 2b, but their assumed performance must respond to the selected climate; mist is a separate delivery method within evaporative cooling. [UK technical definition](https://etl.energysecurity.gov.uk/products/heating-ventilation-air-conditioning-hvac/evaporative-air-coolers).

Heat pipes are optional heat-transfer components needing a suitable heat sink. No reviewed station source establishes them as a principal station-cooling approach. Chilled-water distribution pipes, refrigerant lines and air ducts are distinct components; retain the definitions and sources in design.md.

## Stadium precedents

Historical precedents reviewed 2026-11-05–06, not current operating measurements. Japan National Stadium is now the selected stadium; see its [new dossier](#japan-national-stadium). The current fan/cooling-fan scope supersedes the earlier stadium fan exclusion. Distributed conditioned air also uses fans. No unsupported claim that most stadiums use under-seat cooling.

- **Al Janoub/Al Wakrah:** [engineer interview, 2019](https://www.workerswelfare.qa/en/news/al-wakrah-stadium-cooling-technology.html) describes under-seat diffusers, partial recirculation and geometry limiting infiltration. It distinguishes Khalifa, whose structure required small nozzles. [FIFA, 2022](https://inside.fifa.com/sustainability/news/legacy-in-action-qatars-revolutionary-stadium-cooling-technology) describes pitch/stand delivery. A cold bubble is not an impermeable boundary; no carbon-neutrality/performance claim adopted.
- **Singapore National Stadium:** [Arup](https://www.arup.com/projects/singapore-sports-hub/) and [2016 release](https://www.v2com-newswire.com/en/newsroom/categories/institutional-architecture/press-kits/2186-01/singapore-national-stadium) describe 55,000 seats, under-seat cooled air, movable shading roof and arcade louvres. [MEHITS](https://www.climaveneta.com/EN/projects/1774) plant serves multiple complex areas; do not assign whole-complex thermal capacity to bowl electricity or guarantee comfort in all weather.
- **SoFi / AT&T:** [HKS, July 2026](https://www.hksinc.com/our-news/articles/stadiums-built-to-weather-anything/) contrasts SoFi's open sides/patterned ETFE canopy and natural ventilation with AT&T's operable roof and conditioned interior supplying spectators/players. SoFi's bowl strategy says nothing about every enclosed room. AT&T's closed mode cannot replace the required semi-open case.
- **Kingdom Arena:** [FabricAir supplier account](https://www.fabricair.com/us/news/fabric-ducts-provide-high-iaq-for-record-setting-stadium/) reports over 2.4 km of roof-integrated fabric ducts for a venue described as over 30,000 spectators. Overhead distribution precedent; enclosed venue and supplier comfort claims are not open-bowl performance proof.

Compare low-level, overhead/perimeter and local distribution with shade, geometry, infiltration, recirculation and occupancy. Separate bowl, pitch, concourses and rooms. Radiant cooling remains an extension; heat pipes were not identified as the principal cooling mechanism in these sources.

## Implications for the first case

Hold geometry and shade fixed when comparing the required devices. Test climate dependence and delivered benefit at occupants rather than treating maximum outlet cooling as uniform performance. Include auxiliary electricity, water and maintenance. Enclosed AC is a different boundary; mist and radiant prototypes require their own performance assumptions. No numerical ranking or parameter selection follows from this review.

AI assistance: discovery, evidence comparison, limitations and drafting; these records are not measured project data.
