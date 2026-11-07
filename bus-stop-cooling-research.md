# Cooling a simple open-sided bus shelter

Research date: 2026-11-07. Status: evidence review and modeling recommendations; no technology or climate selected. Sources are primary research, public agencies and technical guidance. No controlled comparison of every method under matching weather, occupancy and resource budgets was identified in this review.

## Interpretation for Problem B

Requirement 2a compares a fan and two sizes of evaporative cooler in an open-sided shelter. Hold shelter geometry and shade constant for that comparison; enclosure with AC changes the case. Shade can be evaluated as a separate design improvement. Distinguish air-temperature reduction, thermal-comfort indices, user feedback, benefit per electricity, and overall effectiveness. Do not rank temperature numbers drawn from different metrics or climates directly.

## Evidence

### Shade: operating bus stops, field measurements and surveys

Dzyuban et al., published online 2021, International Journal of Biometeorology 66 (2022), 345–356. Phoenix bus-stop fieldwork in summer 2018. Average shaded-versus-sun PET reduction was 19°C. PET is physiological equivalent temperature, not air temperature. Effects varied by time and design; shade did not guarantee comfort. This supports treating sun/shade and radiant heat explicitly, not transferring a constant 19°C adjustment to our shelter.

Source, full PDF accessible: https://link.springer.com/content/pdf/10.1007/s00484-021-02074-4.pdf

### Fans: comfort mechanism and unfavorable operator experience

CBE explains how air movement can improve thermal comfort without reducing ambient air temperature. Its indoor reference calculations are not automatically bus-stop calibrations.

Source: https://cbe-berkeley.gitbook.io/fans-guidebook/practitioner-summary/elevated-air-speed-and-thermal-comfort

Singapore Ministry of Transport, 7 May 2026: earlier exposed-bus-stop fan trials had unfavorable commuter feedback; no solar-powered fan rollout planned. It also reports limited ambient-temperature impact, which by itself is not a valid test of fan comfort benefit. Trial layout, weather, speeds and measured comfort data are not disclosed in this statement. No universal fan failure conclusion follows.

Source: https://www.mot.gov.sg/news-resources/newsroom/commuter-comfort-at-bus-stops/

### Evaporative cooling: climate dependence and prototype field evidence

PNNL Building America guidance explains that direct evaporative coolers lower air temperature and add humidity; effectiveness depends on wet-bulb depression, air velocity through media and media condition. It is residential guidance: use mechanism/equation, not residential savings or sizing as open-shelter evidence. Supply temperature can be represented as T_supply=T_dry-epsilon*(T_dry-T_wet); conditions at passengers additionally depend on distribution and mixing. This component effectiveness differs from our human-benefit-per-kWh index.

Source: https://basc.pnnl.gov/resource-guides/evaporative-cooling-systems?existing_homes=602

Guangzhou prototype bus-stop mist study: field measurements and 335 valid questionnaires; indexed publisher abstract reports side spray outperformed top spray and up to 3.1°C air-temperature reduction. Humidity increased. Evidence supports potential benefit even in the tested hot-humid conditions, not universal humid-weather suitability. Mist spray is not the same apparatus as Problem B's wet-pad cooler. Maximum reduction cannot be assumed uniform across space/time.

Source: https://www.sciencedirect.com/science/article/abs/pii/S0378778825015646
Access limit: indexed primary abstract/conclusion available; direct full-page requests returned 403. Do not transfer exact settings, power, water use or reported comfort thresholds without full-method verification.

### Targeted cooled-air delivery: actual operational lesson

Singapore LTA retrospective, 26 April 2024: Airbitat trial at Dhoby Ghaut moved outlets from overhead to columns attached to seats to address cooling and operational feedback. The three-year trial ended in August 2021 because operating/maintenance costs were high relative to typical stops. This supports modeling outlet placement and lifecycle costs; does not establish a measured energy-efficiency ranking or current deployment.

Source: https://www.lta.gov.sg/content/ltagov/en/who_we_are/statistics_and_publications/Connect/bus-stop-shelters.html

### Cooled radiant surfaces: experimental alternative

2023 proof-of-concept study of radiant bus-shelter modules in controlled conditions representing hot dry outdoor weather. The abstract reports useful comfort-index improvements. This is prototype evidence, not established large-scale operating performance or evidence that it beats the three assigned devices. No electrical savings or clinical health protection inferred.

Source: https://www.sciencedirect.com/science/article/pii/S0196890423009731
DOI: 10.1016/j.enconman.2023.117627
Access limit: indexed primary abstract read; direct publisher and university repository requests returned 403.

### Air-conditioned shelter sections: deployed, different boundary

Dubai RTA April 2026 release describes designated air-conditioned sections at main stops alongside shaded outdoor areas. It establishes deployment, not comparative comfort per kWh. An enclosed cooled waiting room is a useful alternative-boundary comparison, not a replacement for the required open-sided shelter.

Source: https://www.rta.ae/wps/portal/rta/ae/home/news-and-media/all-news/NewsDetails/completion-of-726-shelters-for-public-bus-riders

## Proposed use in our model

- Make effective shade the common baseline; compare no active cooling and the three required devices under matched conditions. Shade has capital/maintenance costs even if no cooling electricity is consumed; avoid assigning infinite benefit/energy to zero-energy alternatives.
- Evaluate at least hot-dry and hot-humid weather scenarios before choosing a winner. Targeted evaporative cooling is a strong candidate for dry conditions; fan benefit and evaporation in humid conditions require explicit modeling rather than blanket acceptance/rejection.
- Include solar/radiant exposure, temperature, humidity, natural wind, device delivery/coverage and occupancy/dwell time. Larger power or nominal temperature reduction does not establish higher overall benefit.
- Count electricity, water and maintenance alongside delivered comfort; keep health protection distinct and evidence-based. The Singapore history shows that a physically functioning cooler can still be unattractive operationally.
- No location, weather values, unit interpretation, device sizing or model parameters are adopted by this research note. Next choose climatic scenarios and map supplied device maxima to plausible local performance with explicit uncertainty.

AI assistance: source discovery, evidence comparison, limitations and modeling implications drafted by the assistant. This is a bounded research record, not measured project data.
