---
length_reason: Consolidates source links, deployment evidence, experimental results and access limitations for bus shelters, stations and stadiums.
---

# Cooling research and evidence

Consolidated: 2026-11-07. Bus research was reviewed 2026-11-07; station and stadium sources were reviewed 2026-11-05–06 unless noted. These are evidence records, not newly verified current operating measurements or selected case studies. See [README.md](README.md) for scope/decisions and [design.md](design.md) for model proposals.

## Evidence rules

Distinguish operator-reported deployment, field measurements, controlled prototypes, supplier claims and transferred technical principles. Air-temperature reductions and equivalent-temperature comfort indices are not directly comparable. Missing full-method access stays explicit. No reviewed source establishes a universal winning cooler or clinically validated safety outcome for our venue.

## Bus shelters

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

### Stadium scope clarification

The owner wants realistic systems for an entire large stadium, with strong drafts treated as an undesirable visitor effect. Remove stand-alone fans from the proposed stadium shortlist; the source problem's mandatory bus-shelter fan comparison still applies. This is a scope preference, not evidence that all airflow is unpleasant or that fans are technically incapable of providing comfort. Refrigerated-air distribution itself uses fans; outlet design determines airspeed experienced by spectators.

A documented alternative to under-seat outlets is roof-level distributed fabric ducting: supplier FabricAir reports an installation at Kingdom Arena in Riyadh with more than 2.4 km of ducts integrated into the roof structure, serving a venue it describes as accommodating over 30,000 spectators. The ducts distribute air along their length. Treat stated comfort outcomes as supplier claims and recognize the enclosed venue boundary; this is not proof of performance in a fully open bowl. [FabricAir project account](https://www.fabricair.com/us/news/fabric-ducts-provide-high-iaq-for-record-setting-stadium/)

The stadium-specific discussion should focus on low-level distributed conditioned air, overhead or perimeter duct/nozzle distribution, enclosure plus HVAC, and passive canopy/ventilation strategies, with operating and climate limitations made explicit. Radiant panels remain a research extension rather than a demonstrated replacement at full stadium scale.

### Documented stadium examples

Reviewed 2026-11-05. These are design precedents, not selected case studies or verified performance rankings. Descriptions refer to published designs; no current operating measurements have been obtained. Source claims of carbon neutrality or energy savings are not adopted without a clear accounting boundary and comparison baseline.

#### Al Janoub formerly Al Wakrah in Qatar

The project engineer describes gentle under-seat diffusers, recirculation of some already-cooled air, and stadium geometry designed to reduce warm-wind infiltration. FIFA describes pitch-side nozzles and stand outlets across the cooled Qatar stadiums. The engineering idea is to deliver conditioned air near spectators and players and use the enclosure to help retain it. The stated cold bubble is a design description, not an impermeable air boundary. Wind, openings and mixing remain relevant.

Sources: [project engineer interview, 2019](https://www.workerswelfare.qa/en/news/al-wakrah-stadium-cooling-technology.html); [FIFA cooling overview, 2022](https://inside.fifa.com/sustainability/news/legacy-in-action-qatars-revolutionary-stadium-cooling-technology).

The 2019 interview specifically distinguishes Khalifa: its existing structure prevented the intended under-seat installation, so small nozzles were used instead. Do not assume identical layouts at all Qatar stadiums.

#### Singapore National Stadium

Arup's published design describes a 55,000-seat stadium with cooled air introduced beneath seats, a movable roof providing shade, and louvres protecting the surrounding arcade while permitting airflow. The mechanism combines localized refrigerated-air delivery to spectators with control of solar exposure and natural ventilation. It does not establish that every seat remains comfortable under all weather and event conditions.

Sources: [Arup project page](https://www.arup.com/projects/singapore-sports-hub/); [Arup Associates project release, 2016](https://www.v2com-newswire.com/en/newsroom/categories/institutional-architecture/press-kits/2186-01/singapore-national-stadium). Equipment supplier [MEHITS](https://www.climaveneta.com/EN/projects/1774) describes plant rooms serving multiple areas of the Sports Hub complex; do not assign the entire complex's rated cooling capacity to the spectator bowl or interpret it as electrical consumption.

#### SoFi Stadium in California

HKS describes an open-sided seating bowl under an ETFE canopy. A pattern in the canopy reduces solar heat gain, while open sides admit wind. This is a passive bowl strategy; it should not be interpreted as proof that every enclosed room in the wider venue lacks air conditioning. Inference for our model: wind and weather affect the comfort delivered, so a design description alone cannot establish extreme-heat protection.

#### AT&T Stadium in Texas

HKS describes an operable roof and an air-conditioned interior, with HVAC delivering air at spectator and player locations during hot weather. This demonstrates enclosure plus targeted mechanical cooling. A fully enclosed operating mode is a comparison case; it is not by itself an open-air or semi-open case satisfying the contest's application scope.

Source for SoFi and AT&T: [HKS design explanation, July 2026](https://www.hksinc.com/our-news/articles/stadiums-built-to-weather-anything/).

#### Implications for our design choices

The examples motivate testing outlet placement near occupied zones, shading, enclosure and wind management, recirculation where appropriate, and separate treatment of the seating bowl, pitch, concourses and enclosed rooms. Do not assume cooling capacity or energy reported for a whole venue belongs entirely to the outdoor area. Heat pipes were not identified as the principal cooling mechanism in these reviewed descriptions.

## Implications for the first case

Hold geometry and shade fixed when comparing the required devices. Test climate dependence and delivered benefit at occupants rather than treating maximum outlet cooling as uniform performance. Include auxiliary electricity, water and maintenance. Enclosed AC is a different boundary; mist and radiant prototypes require their own performance assumptions. No numerical ranking or parameter selection follows from this review.

AI assistance: discovery, evidence comparison, limitations and drafting; these records are not measured project data.
