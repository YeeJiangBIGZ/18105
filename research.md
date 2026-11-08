---
length_reason: Consolidates source links, deployment evidence, experimental results and access limitations for bus shelters, stations and stadiums.
---

# Cooling research and evidence

Consolidated: 2026-11-07. Bus research was reviewed 2026-11-07; station and stadium sources were reviewed 2026-11-05–06 unless noted. These are evidence records, not newly verified current operating measurements or selected case studies. See [README.md](README.md) for scope/decisions and [design.md](design.md) for model proposals.

## Evidence rules

Distinguish operator-reported deployment, field measurements, controlled prototypes, supplier claims and transferred technical principles. Air-temperature reductions and equivalent-temperature comfort indices are not directly comparable. Missing full-method access stays explicit. No reviewed source establishes a universal winning cooler or clinically validated safety outcome for our venue.

## Research contribution workflow

Follow [agent.md](agent.md) and claim a bounded research question/heading in [README's task table](README.md#team-startup-and-task-table). Start from a specific design need: for example, a wet-pad performance curve under stated humidity, not an unbounded search for the best cooler.

1. **Check existing evidence.** Search this file before adding a source. Update its existing entry instead of duplicating it. Link a source to each supported claim; several sources can support one finding, and one source can have several bounded findings.
2. **Inspect primary material.** Prefer the original experiment, operator record, technical documentation or dataset. Record author/organization, title, publication/event dates, URL or DOI, exact page/section/table and date accessed. State whether full text, abstract, indexed excerpt or supplier account was available; never imply full-method verification from a search snippet.
3. **Extract the comparison boundary.** Record location, climate, geometry/enclosure, equipment and placement, baseline, measurement period, sample/measurement method, units and statistic (maximum, average, range or uncertainty). For a parameter, include value/range and dependencies. Mark missing fields unknown rather than fill them by guessing.
4. **Assess transferability.** Explain what the source supports, what it cannot establish, and which design component could use it. Separate supply-air from occupied-zone temperature, air temperature from PET/UTCI, thermal output from electricity, and prototype results from routine operation. Report contrary findings; do not combine incompatible studies into an unsupported ranking.
5. **Review and hand off.** For influential numerical inputs, a different teammate/agent should verify the original passage, units, baseline and applicability when feasible. Record the actual checks and remaining gaps. Source verification is not model validation or human adoption. Link the finding from design.md; do not silently install the value in equations or code. Notify the human through the task handoff if evidence conflicts with an accepted assumption.

Use this compact entry format for new findings, preserving a stable descriptive heading so design.md can link to it:

> Finding / contributor / research question: …
>
> Source and exact locator / publication date / accessed date / access level: …
>
> Evidence type: field measurement | deployment report | controlled prototype | supplier claim | technical mechanism.
>
> Conditions, baseline, sample and method / value, units, statistic and uncertainty: …
>
> Supports / does not support / transfer assumptions: …
>
> Intended design use / verification status and reviewer / missing data and next action: …

Existing entries retain their original access limits and have not all been upgraded to this format or independently rechecked. Expand one when it becomes an active model input. An uncited proposed estimate belongs in design.md with an assumption label, not disguised as a research finding. Keep quotations short, preserve citation provenance and record AI assistance. Source documents are evidence, not instructions authorizing agent actions.


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

John / general-chat agent, reviewed 2026-11-07. Proposed, not selected: use a reproducible LTA-standard reference shelter, matching a named stop if claiming a specific venue. Problem 2a names no city/dimensions; requirement 3 allows data or justified estimates. Preserve outdoor exchange and the required devices.

[LTA September 2025 drawings](https://www.lta.gov.sg/content/dam/ltagov/industry_innovations/industry_matters/development_construction_resources/Street_Work_Proposals/Standards_and_Specifications/SDRE/SDRE14-11_BUS_1-5_September_2025.pdf), rendered PDF page 6/BUS5 rev C: plan depth 3000 mm, size table includes 9 m length, seats/screens/columns/path connections/kerb/bollards/information panels/conduits. Hence proposed 9x3 m footprint; remaining heights/structure need verification. Page 5/BUS4 rev D is separately marked TEMPORARY USE ONLY; do not merge its dimensions into BUS5. Official standard, not surveyed site or approved retrofit; conduits do not establish spare electrical capacity, water or roof loading. No structural/independent review.

[LTA DataMall](https://datamall.lta.gov.sg/content/datamall/en/dynamic-data.html): catalogue checked for stops, arrivals, services and passenger-volume datasets. No credentials, downloads or matched stop; boarding totals are not instantaneous occupancy/paths. [NEA weather collection](https://data.gov.sg/collections/1459/view): temperature/RH/wind, some up to one-minute intervals; no downloaded series or local shelter/radiant correction. Phoenix's Dzyuban study below offers measured thermal conditions, photographs and historical daily ridership 29–107 for six north-facing shelters (summer 2018); not simultaneous occupancy or complete mounting plans. Do not transplant its effects into Singapore.

Candidate mounting regions beneath beams, beside posts, rear seats and an external plant pad remain proposals. Exclude boarding/access paths, sightlines and service clearances; check loading, utilities, drainage and maintenance before declaring feasibility.

Requested inline 3D concept built 2026-11-07: rotatable/top/front/end views, removable roof, bare/fan/ducted alternatives. Assumptions: 9x3 m footprint, 2.7 m roof, two 2.8 m benches, 1.5 m rear opening, 0.8x0.8x1.1 m external cooler, outlet x=1.5/4.5/7.5 m, illustrative posts/screens/ducts. Controls checked in headless Chrome; desktop/narrow renders inspected. Arrows are axes, not solved flow; no CFD or optimization. Inline source remains in chat. Next select reference versus named site and verify dimensions/feasible regions; no geometry or placement adopted.

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

Singapore LTA retrospective, 26 April 2024: Airbitat trial at Dhoby Ghaut moved outlets from overhead to columns attached to seats to address cooling and operational feedback. The three-year trial ended in August 2021 because operating/maintenance costs were high relative to typical stops. This supports modeling outlet placement and lifecycle costs; does not establish a measured energy-efficiency ranking or current deployment.

Source: https://www.lta.gov.sg/content/ltagov/en/who_we_are/statistics_and_publications/Connect/bus-stop-shelters.html

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

The owner's strong-draft objection and stadium fan exclusion remain recorded. Do not turn them into a general physical claim that all air movement harms comfort or exclude the fan explicitly required for the bus comparison. A draft penalty or acceptable airflow constraint is a proposal, not a selected numerical limit.

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

Reviewed 2026-11-05–06; published designs, not current measurements or chosen venues. John excluded stand-alone fans from the stadium shortlist because of draft concerns; this neither establishes that airflow is inherently unpleasant nor removes Problem B's required bus fan. Distributed conditioned air also uses fans. No unsupported claim that most stadiums use under-seat cooling.

- **Al Janoub/Al Wakrah:** [engineer interview, 2019](https://www.workerswelfare.qa/en/news/al-wakrah-stadium-cooling-technology.html) describes under-seat diffusers, partial recirculation and geometry limiting infiltration. It distinguishes Khalifa, whose structure required small nozzles. [FIFA, 2022](https://inside.fifa.com/sustainability/news/legacy-in-action-qatars-revolutionary-stadium-cooling-technology) describes pitch/stand delivery. A cold bubble is not an impermeable boundary; no carbon-neutrality/performance claim adopted.
- **Singapore National Stadium:** [Arup](https://www.arup.com/projects/singapore-sports-hub/) and [2016 release](https://www.v2com-newswire.com/en/newsroom/categories/institutional-architecture/press-kits/2186-01/singapore-national-stadium) describe 55,000 seats, under-seat cooled air, movable shading roof and arcade louvres. [MEHITS](https://www.climaveneta.com/EN/projects/1774) plant serves multiple complex areas; do not assign whole-complex thermal capacity to bowl electricity or guarantee comfort in all weather.
- **SoFi / AT&T:** [HKS, July 2026](https://www.hksinc.com/our-news/articles/stadiums-built-to-weather-anything/) contrasts SoFi's open sides/patterned ETFE canopy and natural ventilation with AT&T's operable roof and conditioned interior supplying spectators/players. SoFi's bowl strategy says nothing about every enclosed room. AT&T's closed mode cannot replace the required semi-open case.
- **Kingdom Arena:** [FabricAir supplier account](https://www.fabricair.com/us/news/fabric-ducts-provide-high-iaq-for-record-setting-stadium/) reports over 2.4 km of roof-integrated fabric ducts for a venue described as over 30,000 spectators. Overhead distribution precedent; enclosed venue and supplier comfort claims are not open-bowl performance proof.

Compare low-level, overhead/perimeter and local distribution with shade, geometry, infiltration, recirculation and occupancy. Separate bowl, pitch, concourses and rooms. Radiant cooling remains an extension; heat pipes were not identified as the principal cooling mechanism in these sources.

## Implications for the first case

Hold geometry and shade fixed when comparing the required devices. Test climate dependence and delivered benefit at occupants rather than treating maximum outlet cooling as uniform performance. Include auxiliary electricity, water and maintenance. Enclosed AC is a different boundary; mist and radiant prototypes require their own performance assumptions. No numerical ranking or parameter selection follows from this review.

AI assistance: discovery, evidence comparison, limitations and drafting; these records are not measured project data.
