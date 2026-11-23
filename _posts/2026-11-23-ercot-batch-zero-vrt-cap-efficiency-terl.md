---
title: "ERCOT’s 31% ride-through pass rate; Spain’s 80% hourly-matched access rule; most of a 6.3% bill cut is efficiency"
date: 2026-11-23 08:30:00 +0800
categories: [Daily Brief, Power]
tags: [grid, ride-through, power-capping, ramp-smoothing, AIDC-infra, industry, academia, oversubscription, inference, ERCOT]
description: "A 5-minute cut. ERCOT’s preliminary Batch Zero voltage ride-through tests of about 260 large-load projects, presented on 19 November, show that 31% of the tested models rode through and 69% failed, mostly by full or partial load loss. On 20 November Spain approved a royal decree that ties grid access for data centers above 10 MW to 80% hourly-matched additional renewables, with a looser path for sites that join an automatic power-reduction scheme. Zhou and Cavraro (arXiv 2611.26572) find that a 210,000-GPU fleet scheduled against 2025 CAISO day-ahead prices cuts energy cost 6.3% at equal work, but 3.8 percentage points are price-blind efficiency from lower GPU caps; only 2.3 points are temporal price response and 0.2 points are routing."
media_subpath: /assets/img/briefs/2026-11-23/
image:
  path: fig-cost-saving-split.png
  alt: "Bar chart of energy-cost savings in Zhou and Cavraro, arXiv 2611.26572, a year-long 2025 CAISO simulation: 3.8 percent from price-blind efficiency, 2.3 percent from temporal price response, 0.2 percent from spatial routing, and a 6.3 percent fleet total."
---

## At a glance

- **Most tested Batch Zero models do not ride through.** On 19 November, [ERCOT](https://www.ercot.com/ "Electric Reliability Council of Texas: the grid operator for most of Texas.") told its [Large Load Working Group](https://www.ercot.com/calendar/11192026-LLWG-Meeting "ERCOT Large Load Working Group meeting, 19 November 2026, 9:30 a.m. Central, Austin and WebEx.") that [preliminary voltage ride-through tests](https://www.ercot.com/files/docs/2026/11/18/4.-BZ-VRT-Review-and-Next-Steps_Nov2026-LLWG.pdf "ERCOT, Batch Zero Voltage Ride-Through Review and Next Steps, 18 November 2026 LLWG deck.") of about 260 large-load projects showed a 31% pass rate and a 69% fail rate, mostly from load loss. Without demonstrated ride-through, projects are not eligible for the [Quarterly Stability Assessment](https://www.ercot.com/files/docs/2026/11/18/4.-BZ-VRT-Review-and-Next-Steps_Nov2026-LLWG.pdf "The 18 November 2026 ERCOT deck states that QSA is a prerequisite for Initial Energization.") required before Initial Energization.
- **Spain ties access above 10 MW to 80% hourly-matched renewables.** On 20 November the Council of Ministers approved a [MITECO](https://www.miteco.gob.es/ "Ministerio para la Transición Ecológica y el Reto Demográfico: Spain’s ministry for ecological transition.") [royal decree](https://www.miteco.gob.es/es/prensa/ultimas-noticias/2026/noviembre/el-gobierno-aprueba-el-real-decreto-para-la-sostenibilidad-energ.html "MITECO press note, 20 November 2026: Council of Ministers approval of the data-center sustainability royal decree.") that conditions grid access above 10 MW on 80% renewable electricity, matched hour by hour. Sites that join an automatic power-reduction scheme may use a looser five-year path.
- **A 6.3% energy-bill cut is mostly a lower cap.** Zhou and Cavraro at the [National Laboratory of the Rockies](https://www.nlr.gov/ "National Laboratory of the Rockies (NLR), Golden, Colorado.") (arXiv [2611.26572](https://arxiv.org/abs/2611.26572 "Zhou and Cavraro, Optimal Scheduling of Multi-Site AI Data Centers in Day-Ahead Markets, arXiv 2611.26572, submitted 19 November 2026.")) schedule a 210,000-GPU fleet against 2025 [CAISO](https://www.caiso.com/ "California Independent System Operator: grid operator for most of California and part of Nevada.") day-ahead prices. At equal work, cost falls 6.3%: 3.8 percentage points from price-blind [GPU power caps](https://en.wikipedia.org/wiki/Thermal_design_power "Power capping: running a GPU below its thermal design power (TDP) to limit draw, usually with some loss of throughput."), 2.3 from shifting work in time, and 0.2 from routing between sites.

## Key developments

### 1. ERCOT’s preliminary Batch Zero tests: 31% of models ride through; 69% fail · 18–20 Nov 2026 · industry / grid

ERCOT’s 18 November deck, presented the next morning, reports [voltage ride-through](https://lizhouyu.github.io/technical_posts/posts/caiso-20mw-pjm-fast-energization-gfm-halls/ "Ride-through: remaining connected through a grid fault or voltage sag.") tests of about 260 Batch Zero large-load projects, run from September to November 2026 against Nodal Operating Guide Section 2.15. “Preliminary results indicate that 31% of the tested LCLs rode through the voltage disturbance.” 69% failed. Of the deficiencies, 68% were full or partial load loss and 24% were slow recovery. Some projects may not have been tested. Detailed results are due in early December 2026. Projects subject to the rule “will not be eligible for QSA if their dynamic models do not demonstrate the applicable ride-through performance,” and without that assessment they will not be granted Initial Energization.

Implication: In ERCOT, ride-through is now an interconnection gate, not a best practice. A preliminary 69% model-failure rate — mostly load loss — is a warning for [oversubscription](https://lizhouyu.github.io/technical_posts/posts/power-oversubscription-brief/ "Power oversubscription: contracting or operating more IT load than the upstream power path can supply at coincident peak.") and [ramp-smoothing](https://lizhouyu.github.io/technical_posts/posts/aidc-power-ramp-smoothing/ "Power ramp smoothing: using storage, caps or scheduling so that fast AI load steps do not appear as equally fast ramps at the grid.") designs that assume the IT load stays connected through a sag.

**Sources:** [ERCOT Batch Zero VRT deck, 18 Nov](https://www.ercot.com/files/docs/2026/11/18/4.-BZ-VRT-Review-and-Next-Steps_Nov2026-LLWG.pdf "Primary source of the ~260, 31%, 69%, 68% and 24% figures and of the QSA/energization gate."); [LLWG 19 Nov agenda](https://www.ercot.com/calendar/11192026-LLWG-Meeting "Agenda item 3: ERCOT’s Voltage Ride-Through Review for LCLs in Batch Zero.").

### 2. Spain conditions access above 10 MW on 80% hourly-matched renewables, or on a flexibility bargain · 20 Nov 2026 · industry / grid

Data centers of more than 10 MW must justify 80% renewable consumption with hourly correlation, under an [additionality](https://www.miteco.gob.es/es/prensa/ultimas-noticias/2026/noviembre/el-gobierno-aprueba-el-real-decreto-para-la-sostenibilidad-energ.html "Additionality: the renewable generation generally must have entered the system no more than 36 months before the data center starts, with stated exceptions.") rule that generally requires the generation to have entered the system no more than 36 months before the data center starts. Self-consumption, storage, and supply contracts longer than six years may count. The 80% rule runs until renewables exceed 90% of the national mix. Alternatively, for five years, sites that join the [Sistema de Reducción Automática de Potencia](https://www.miteco.gob.es/es/prensa/ultimas-noticias/2026/noviembre/el-gobierno-aprueba-el-real-decreto-para-la-sostenibilidad-energ.html "Sistema de Reducción Automática de Potencia: Spain’s automatic power-reduction scheme, with priority disconnection, as described in the 20 November MITECO note.") — with priority disconnection — may justify 60% additional renewables in peak hours (P1) until 31 December 2028, then 70% in peak and shoulder hours (P1 and P2). Non-compliance can suspend access and connection rights for three years, plus automatic bill compensations. Interim caps are a [WUE](https://en.wikipedia.org/wiki/Data_center#Energy_use "Water usage effectiveness (WUE): water used by the facility, typically in liters per kilowatt-hour of IT energy; the decree’s transitional cap is 0.1.") of 0.1 or less and a [PUE](https://en.wikipedia.org/wiki/Power_usage_effectiveness "Power usage effectiveness (PUE): facility power divided by IT power; the decree’s transitional cap is 1.25.") of 1.25 or less. Vice-president Sara Aagesen said that without the decree the bill impact would be EUR 5 billion and industrial consumers would pay 25% more — estimates from the ministry note.

Implication: Grid access in Spain is now a renewable-and-flexibility bargain: the automatic power-reduction path trades a looser renewable share for formal curtailment, so oversubscription and ramp smoothing become compliance tools, not only engineering ones.

**Sources:** [MITECO note, 20 Nov](https://www.miteco.gob.es/es/prensa/ultimas-noticias/2026/noviembre/el-gobierno-aprueba-el-real-decreto-para-la-sostenibilidad-energ.html "Primary source of the 10 MW threshold, 80% hourly-matched rule, 36-month additionality, storage credit, 60%/70% flexibility path, penalties, interim WUE/PUE, and the minister’s EUR 5 billion and 25% claims.").

### 3. Most of a 6.3% energy-bill cut is a lower GPU cap, not a grid service · submitted 19 Nov 2026 · academia / capping

Xinyang Zhou and Guido Cavraro (arXiv [2611.26572](https://arxiv.org/abs/2611.26572 "Zhou and Cavraro, arXiv 2611.26572, submitted 19 November 2026.")) write a linear program that maps GPU power-cap levels, job timing and placement onto hourly facility power and [locational marginal prices](https://en.wikipedia.org/wiki/Locational_marginal_pricing "Locational marginal price (LMP): the marginal cost of supplying the next megawatt-hour at a specific grid node."). They simulate 210,000 GPUs (90,000 in Silicon Valley, 60,000 in Los Angeles, 60,000 in San Diego) against 2025 CAISO day-ahead prices. Uncoordinated, the fleet averages about 190 MW with a mean daily peak of 229.2 MW. The fleet is a price taker, the workload is known a day ahead, and PUE is a constant 1.1. Fleet coordination cuts energy cost by 6.3%, or about USD 4.1 million a year: 3.8 percentage points from price-blind efficiency (lower caps on inference and short jobs, cutting energy 4.7% and the mean daily peak 16%); 2.3 points from responding to prices; and 0.2 points from routing between sites, which exceeds 1% on only 23 days. At 46% of TDP, an inference GPU is about 1.2 times slower; training’s efficiency gain is under 1%.

Implication: For oversubscription and flexible interconnection, the headline 6.3% is the wrong number. Most of it is a cheaper operating point that does not need a price signal. Only the 2.5 percentage points from time-shifting and routing are a grid service. This is a year-long simulation with perfect day-ahead knowledge, not a measured hall.

![Where a 6.3% energy-cost saving comes from in a 2025 CAISO fleet simulation](fig-cost-saving-split.png){: w="2040" h="1020" }
_Figure 1. Cost-saving split in Zhou and Cavraro, arXiv 2611.26572._

**Sources:** [arXiv 2611.26572](https://arxiv.org/abs/2611.26572 "Abstract and HTML: 6.3%, 3.8%, 2.3%, 0.2%, Table III, and the 210,000-GPU setup.") and the [HTML full text](https://arxiv.org/html/2611.26572 "Source of Table II, Table III, the 4.7% energy cut, 16% peak cut, and the 46% TDP result.").

## Spotlight: efficiency is not flexibility

Zhou and Cavraro state the accounting trap directly: an AI fleet can cut its bill by running at a lower cap, by shifting work in time, or by moving work between sites, “yet all three appear as savings when an optimized schedule is compared with a fleet that runs every job at full power on arrival, which counts efficiency as flexibility.” In their year that comparison yields 6.3%; the price-responsive slice is 2.5 percentage points. Oversubscription credits and flexible-interconnection offers should quote the slice that answers a price or a reliability signal.

## Bottom line

ERCOT is gating Batch Zero energization on demonstrated ride-through, and most tested models are not there yet. Spain is gating access on hourly-matched renewables, with a formal curtailment bargain as the alternative. The largest bill cut in the CAISO study is a lower cap, not a ramp service. ERCOT’s figures are preliminary model tests; Spain’s bill-impact figures are ministerial estimates; the academic numbers are simulations.

## Also noted

- The [IEA](https://www.iea.org/ "International Energy Agency.") [World Energy Outlook 2026](https://www.iea.org/reports/world-energy-outlook-2026/overview-and-key-findings "IEA, World Energy Outlook 2026, overview and key findings. The 1,000 TWh STEPS line is on this page.") (19 November) has data-center electricity doubling to 1,000 TWh by 2030 in the [STEPS](https://www.iea.org/reports/world-energy-outlook-2026/overview-and-key-findings "Stated Policies Scenario (STEPS): the IEA’s scenario based on today’s policy settings.") case. The [full report](https://www.iea.org/files/1027b259-ce5a-4f0d-8d03-3ba0338eaa18/WorldEnergyOutlook2026.pdf "Official WEO 2026 PDF. The battery and SST sentences are in Chapter 1, beside Figure 1.38.") estimates that “battery demand from data centres reaches around 25 GW by 2030,” and that [solid-state transformers](https://en.wikipedia.org/wiki/Solid-state_transformer "Solid-state transformer (SST): a power-electronic transformer from medium-voltage AC to a controlled DC or AC output.") “are also being developed.” Forecasts, not installed capacity.
- [Google](https://www.googlecloudpresscorner.com/2026-11-19-Google-and-Ohio-Power-Company-Announce-New-Initiative-to-Unlock-New-Capacity-with-Advanced-Transmission-Technology "Google and Ohio Power Company press release, 19 November 2026.") and Ohio Power Company (19 November) propose reconductoring 15.5 miles of Columbus lines, funded by Google at an incremental USD 10.8 million, to deliver 24 MW about two years early, and later “more than 700 MW” after a planned 765 kV buildout, late 2028 if approved by [PUCO](https://puco.ohio.gov/ "Public Utilities Commission of Ohio."). A filing, not an approval.
- Zhang, Zhang, Wang and Sui (arXiv [2611.26527](https://arxiv.org/abs/2611.26527 "Zhang, Zhang, Wang and Sui, TERL, arXiv 2611.26527, submitted 19 November 2026.")): 1-second GPU-power forecasts on MIT Supercloud telemetry with nMAE of 0.82–1.18% across regimes, against 4–11% for the baselines — a one-second look-ahead on cluster telemetry, not a hall-level forecast.

## Glossary

- [**AIDC**](https://lizhouyu.github.io/technical_posts/posts/aidc-power-stack-and-shortlist/): AI data center.
- [**Additionality**](https://www.miteco.gob.es/es/prensa/ultimas-noticias/2026/noviembre/el-gobierno-aprueba-el-real-decreto-para-la-sostenibilidad-energ.html): The decree’s rule that the renewable generation generally must have entered the system no more than 36 months before the data center starts.
- [**Batch Zero**](https://www.ercot.com/files/docs/2026/11/18/4.-BZ-VRT-Review-and-Next-Steps_Nov2026-LLWG.pdf): ERCOT’s first batched study group of large-load interconnection projects.
- [**BESS**](https://en.wikipedia.org/wiki/Grid_energy_storage): Battery energy storage system.
- [**CAISO**](https://www.caiso.com/): California Independent System Operator.
- [**ERCOT**](https://www.ercot.com/): Electric Reliability Council of Texas.
- [**LMP**](https://en.wikipedia.org/wiki/Locational_marginal_pricing): Locational marginal price.
- [**MITECO**](https://www.miteco.gob.es/): Spain’s ministry for ecological transition.
- [**nMAE**](https://en.wikipedia.org/wiki/Mean_absolute_error): Normalized mean absolute error.
- [**Oversubscription**](https://lizhouyu.github.io/technical_posts/posts/power-oversubscription-brief/): Contracting or operating more IT load than the upstream path can supply at coincident peak.
- [**PUE**](https://en.wikipedia.org/wiki/Power_usage_effectiveness): Power usage effectiveness.
- [**QSA**](https://www.ercot.com/files/docs/2026/11/18/4.-BZ-VRT-Review-and-Next-Steps_Nov2026-LLWG.pdf): Quarterly Stability Assessment, which ERCOT treats as a prerequisite for Initial Energization.
- [**Ride-through**](https://lizhouyu.github.io/technical_posts/posts/caiso-20mw-pjm-fast-energization-gfm-halls/): Remaining connected through a grid fault or voltage sag.
- [**SST**](https://en.wikipedia.org/wiki/Solid-state_transformer): Solid-state transformer.
- [**STEPS**](https://www.iea.org/reports/world-energy-outlook-2026/overview-and-key-findings): The IEA’s Stated Policies Scenario.
- [**TDP**](https://en.wikipedia.org/wiki/Thermal_design_power): Thermal design power.
- [**UPS**](https://en.wikipedia.org/wiki/Uninterruptible_power_supply): Uninterruptible power supply.
- [**VRT**](https://en.wikipedia.org/wiki/Fault_ride_through): Voltage ride-through.
- [**WUE**](https://en.wikipedia.org/wiki/Data_center#Energy_use): Water usage effectiveness.

---

_How useful was today’s brief? Reply in Grok Bot chat with an overall rating (1–5) and, if you like, per-item ratings (1–5)._
