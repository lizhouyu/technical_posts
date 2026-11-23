---

title: "Only 31% of ERCOT Batch Zero models ride through; most of a 6.3% bill cut is efficiency, not flexibility"
date: 2026-11-23 08:30:00 +0800
categories: [Daily Brief, Power]
tags: [grid, ride-through, power-capping, ramp-smoothing, AIDC-infra, industry, academia, oversubscription, inference, ERCOT]
description: "A 5-minute cut. ERCOT’s preliminary Batch Zero voltage ride-through tests of about 260 large-load projects, presented on 19 November, show that 31% of the tested models rode through and 69% failed, mostly by full or partial load loss. Zhou and Cavraro (arXiv 2611.26572) find that a 210,000-GPU fleet scheduled against 2025 CAISO day-ahead prices cuts energy cost 6.3% at equal work, but 3.8 percentage points are price-blind efficiency from lower GPU caps; only 2.3 points are temporal price response and 0.2 points are routing. TERL (arXiv 2611.26527) holds 1-second GPU-power forecast error near 1% across idle, busy, and ramping regimes on MIT Supercloud telemetry."
media_subpath: /assets/img/briefs/2026-11-23/
image:
  path: fig-cost-saving-split.png
  alt: "Bar chart of energy-cost savings in Zhou and Cavraro, arXiv 2611.26572, a year-long 2025 CAISO simulation: 3.8 percent from price-blind efficiency, 2.3 percent from temporal price response, 0.2 percent from spatial routing, and a 6.3 percent fleet total."
---

## At a glance

- **Most tested Batch Zero models do not ride through.** On 19 November, [ERCOT](https://www.ercot.com/ "Electric Reliability Council of Texas: the grid operator for most of Texas.") told its [Large Load Working Group](https://www.ercot.com/calendar/11192026-LLWG-Meeting "ERCOT Large Load Working Group meeting, 19 November 2026, 9:30 a.m. Central, Austin and WebEx.") that [preliminary voltage ride-through tests](https://www.ercot.com/files/docs/2026/11/18/4.-BZ-VRT-Review-and-Next-Steps_Nov2026-LLWG.pdf "ERCOT, Batch Zero Voltage Ride-Through Review and Next Steps, 18 November 2026 LLWG deck.") of about 260 large-load projects showed a 31% pass rate and a 69% fail rate, mostly from load loss. These are model tests, not field measurements. Without a demonstrated ride-through, Batch Zero projects are not eligible for the [Quarterly Stability Assessment](https://www.ercot.com/files/docs/2026/11/18/4.-BZ-VRT-Review-and-Next-Steps_Nov2026-LLWG.pdf "The 18 November 2026 ERCOT deck states that QSA is a prerequisite for Initial Energization.") required before Initial Energization.
- **A 6.3% energy-bill cut is mostly a lower cap.** Zhou and Cavraro at the [National Laboratory of the Rockies](https://www.nlr.gov/ "National Laboratory of the Rockies (NLR), Golden, Colorado.") (arXiv [2611.26572](https://arxiv.org/abs/2611.26572 "Zhou and Cavraro, Optimal Scheduling of Multi-Site AI Data Centers in Day-Ahead Markets, arXiv 2611.26572, submitted 19 November 2026.")) schedule a 210,000-GPU fleet against 2025 [CAISO](https://www.caiso.com/ "California Independent System Operator: grid operator for most of California and part of Nevada.") day-ahead prices. At equal work, cost falls 6.3%: 3.8 percentage points from price-blind [GPU power caps](https://en.wikipedia.org/wiki/Thermal_design_power "Power capping: running a GPU below its thermal design power (TDP) to limit draw, usually with some loss of throughput."), 2.3 from shifting work in time, and 0.2 from routing between sites. Simulation; the workload is known a day ahead.
- **A 1-second forecast holds near 1% error through ramps.** Zhang, Zhang, Wang and Sui (arXiv [2611.26527](https://arxiv.org/abs/2611.26527 "Zhang, Zhang, Wang and Sui, Thermal-Guided Ensemble Reinforcement Learning for Regime-Adaptive Short-Term GPU Power Forecasting in AI Data Centers, arXiv 2611.26527, submitted 19 November 2026.")) report a [normalized mean absolute error](https://en.wikipedia.org/wiki/Mean_absolute_error "Normalized mean absolute error (nMAE): mean absolute forecast error divided by the mean of the training load.") of 0.82–1.18% on 1-second [MIT Supercloud](https://arxiv.org/abs/2611.26527 "The paper evaluates TERL on the MIT Supercloud 1-second GPU telemetry dataset cited as Samsi et al., HPEC 2021.") telemetry, against 4–11% for the baselines. The look-ahead is one second; this is cluster telemetry in watts, not a hall-level ramp forecast.

## Key developments

### 1. ERCOT’s preliminary Batch Zero tests: 31% of models ride through; 69% fail · 18–20 Nov 2026 · industry / grid

ERCOT’s 18 November deck, presented the next morning, reports [voltage ride-through](https://lizhouyu.github.io/technical_posts/posts/caiso-20mw-pjm-fast-energization-gfm-halls/ "Ride-through: remaining connected through a grid fault or voltage sag.") tests of about 260 Batch Zero large-load projects, run from September to November 2026 against Nodal Operating Guide Section 2.15. “Preliminary results indicate that 31% of the tested LCLs rode through the voltage disturbance.” 69% failed. Of the deficiencies, 68% were full or partial load loss and 24% were slow recovery; some projects failed for more than one reason. Projects that lacked required dynamic models, or that missed preliminary Base Load or Studied Load requirements, may not have been tested. Detailed results are due in early December 2026; updated models may be filed by January 2027. Batch Zero projects subject to the rule “will not be eligible for QSA if their dynamic models do not demonstrate the applicable ride-through performance,” and without that assessment they will not be granted Initial Energization.

Implication: In ERCOT, ride-through is now an interconnection gate, not a best practice. A preliminary 69% model-failure rate — mostly load loss — is a warning for [oversubscription](https://lizhouyu.github.io/technical_posts/posts/power-oversubscription-brief/ "Power oversubscription: contracting or operating more IT load than the upstream power path can supply at coincident peak.") and [ramp-smoothing](https://lizhouyu.github.io/technical_posts/posts/aidc-power-ramp-smoothing/ "Power ramp smoothing: using storage, caps or scheduling so that fast AI load steps do not appear as equally fast ramps at the grid.") designs that assume the IT load stays connected through a sag. These are model tests, not field measurements.

**Sources:** [ERCOT Batch Zero VRT deck, 18 Nov](https://www.ercot.com/files/docs/2026/11/18/4.-BZ-VRT-Review-and-Next-Steps_Nov2026-LLWG.pdf "Primary source of the ~260, 31%, 69%, 68% and 24% figures and of the QSA/energization gate."); [LLWG 19 Nov agenda](https://www.ercot.com/calendar/11192026-LLWG-Meeting "Agenda item 3: ERCOT’s Voltage Ride-Through Review for LCLs in Batch Zero."); [Energy Central, 20 Nov](https://www.energycentral.com/energy-management/post/news-ercot-has-ordered-data-centers-to-ride-through-grid-disturbances--C8th9icDumY4anQ "Secondary contemporaneous report of the 31%/69% preliminary result.").

### 2. Most of a 6.3% energy-bill cut is a lower GPU cap, not a grid service · submitted 19 Nov 2026 · academia / capping

Xinyang Zhou and Guido Cavraro (arXiv [2611.26572](https://arxiv.org/abs/2611.26572 "Zhou and Cavraro, arXiv 2611.26572, submitted 19 November 2026.")) write a linear program that maps GPU power-cap levels, job timing and placement onto hourly facility power and [locational marginal prices](https://en.wikipedia.org/wiki/Locational_marginal_pricing "Locational marginal price (LMP): the marginal cost of supplying the next megawatt-hour at a specific grid node."). They simulate 210,000 GPUs (90,000 in Silicon Valley, 60,000 in Los Angeles, 60,000 in San Diego) against 2025 CAISO day-ahead prices. Uncoordinated, the fleet averages about 190 MW with a mean daily peak of 229.2 MW, and every mode completes the same work. The fleet is a price taker, the workload is known a day ahead, and [PUE](https://en.wikipedia.org/wiki/Power_usage_effectiveness "Power usage effectiveness (PUE): facility power divided by IT power; 1.1 is a hyperscale-like constant used in the paper.") is a constant 1.1.

Fleet coordination cuts energy cost by 6.3%, or about USD 4.1 million a year. Nested modes split that saving: 3.8 percentage points from price-blind efficiency (lower caps on inference and short jobs, cutting energy 4.7% and the mean daily peak 16%); 2.3 points from responding to prices (the average price paid falls 3.6%); and 0.2 points from routing between sites, which exceeds 1% on only 23 days. At 46% of TDP, an inference GPU is about 1.2 times slower. Training’s efficiency gain is under 1%.

Implication: For oversubscription and flexible interconnection, the headline 6.3% is the wrong number. Most of it is a cheaper operating point that does not need a price signal. Only the 2.5 percentage points from time-shifting and routing are a grid service, and routing is small inside one ISO. This is a year-long simulation with perfect day-ahead knowledge, not a measured hall.

![Where a 6.3% energy-cost saving comes from in a 2025 CAISO fleet simulation](fig-cost-saving-split.png){: w="2040" h="1020" }
_Figure 1. Cost-saving split in Zhou and Cavraro, arXiv 2611.26572 (2025 CAISO day-ahead simulation; equal work)._

**Sources:** [arXiv 2611.26572](https://arxiv.org/abs/2611.26572 "Abstract and HTML: 6.3%, 3.8%, 2.3%, 0.2%, Table III, and the 210,000-GPU setup."); [HTML full text](https://arxiv.org/html/2611.26572 "Source of Table II, Table III, the 4.7% energy cut, 16% peak cut, and the 46% TDP result.").

### 3. A 1-second GPU-power forecast that holds near 1% error through ramps · submitted 19 Nov 2026 · academia / ramp smoothing

Yuanshuo Zhang, Ying Zhang and Ziying Wang ([Oklahoma State University](https://www.okstate.edu/ "Oklahoma State University.")) and Fanping Sui ([UC Berkeley](https://www.berkeley.edu/ "University of California, Berkeley.")) (arXiv [2611.26527](https://arxiv.org/abs/2611.26527 "Zhang, Zhang, Wang and Sui, arXiv 2611.26527, submitted 19 November 2026.")) propose TERL, a thermal-guided ensemble that reweights base predictors at each step and corrects residuals with GPU and memory temperature. On 1-second MIT Supercloud telemetry, TERL’s nMAE is 0.82% idle, 0.91% busy, 1.18% ramping up and 1.05% ramping down, against 4–11% for the baselines. On a step from about 90 W to 400 W, TERL follows within one sample; the baselines lag and then bias by up to 50 W. The look-ahead horizon is 1 second.

Implication: A forecast that holds through a one-second step is useful at the cap and converter layer. It is not a substitute for minute-to-hour [BESS](https://en.wikipedia.org/wiki/Grid_energy_storage "Battery energy storage system (BESS): a battery plus inverter used for backup, ramp smoothing or grid services.") smoothing or for interconnection ramp limits. The traces are academic-cluster telemetry in watts, not a multi-megawatt hall, and a 1-second horizon cannot see a job start in advance.

**Sources:** [arXiv 2611.26527](https://arxiv.org/abs/2611.26527 "Abstract: about 1% nMAE versus 4–11% baselines."); [HTML full text](https://arxiv.org/html/2611.26527 "Table I regime nMAE, the 90 W to 400 W step, and the 1-second horizon.").

## Spotlight: efficiency is not flexibility

Zhou and Cavraro state the accounting trap directly: an AI fleet can cut its bill by running at a lower cap, by shifting work in time, or by moving work between sites, “yet all three appear as savings when an optimized schedule is compared with a fleet that runs every job at full power on arrival, which counts efficiency as flexibility.” In their year, that comparison yields 6.3%; the price-responsive slice is 2.5 percentage points. Oversubscription credits and flexible-interconnection offers should quote the slice that answers a price or a reliability signal, not the headline that includes a cheaper steady-state operating point.

## Bottom line

ERCOT is gating Batch Zero energization on demonstrated ride-through, and most of the models it has tested are not there yet. On the IT side, the largest bill cut in a careful CAISO study is a lower cap on inference and short jobs, not a ramp service. Second-scale forecasts can tighten that cap layer; they do not replace storage or ride-through design. ERCOT’s figures are preliminary model tests; the academic numbers are simulations.

## Also noted

- Vasquez-Plaza, Subedi, Dong and Pinto, [ORNL](https://www.ornl.gov/ "Oak Ridge National Laboratory (ORNL).") (arXiv [2611.25512](https://arxiv.org/abs/2611.25512 "Vasquez-Plaza et al., Physics-Guided Multi-Output Surrogate Modeling of a Centralized-UPS Data Center, arXiv 2611.25512, submitted 19 November 2026. PESGM 2027 preprint.")): a NARX surrogate of a simulated 1 MW centralized-[UPS](https://en.wikipedia.org/wiki/Uninterruptible_power_supply "Uninterruptible power supply (UPS): a converter and energy buffer that conditions facility power and can ride through short interruptions.") data center has a mean four-output test error of 0.1441% on a 1 MVA base; a three-phase realization tracks two 41-second AI profiles with RMSEs of 0.604 kW / 0.353 kvar and 1.539 kW / 0.442 kvar.
- Bera et al. (arXiv [2611.25176](https://arxiv.org/abs/2611.25176 "Bera et al., Reliability-based Sizing of Energy Storage for Large Load Integration, arXiv 2611.25176, submitted 18 November 2026. CIGRE US National Committee Grid of the Future Symposium 2026.")): energy-storage sizing and siting for AI large loads on the RTS-GMLC 72-bus system (no MW rating in the abstract).

## Glossary

- [**AIDC**](https://lizhouyu.github.io/technical_posts/posts/aidc-power-stack-and-shortlist/): AI data center.
- [**Batch Zero**](https://www.ercot.com/files/docs/2026/11/18/4.-BZ-VRT-Review-and-Next-Steps_Nov2026-LLWG.pdf): ERCOT’s first batched study group of large-load interconnection projects.
- [**BESS**](https://en.wikipedia.org/wiki/Grid_energy_storage): Battery energy storage system.
- [**CAISO**](https://www.caiso.com/): California Independent System Operator.
- [**ERCOT**](https://www.ercot.com/): Electric Reliability Council of Texas.
- [**LMP**](https://en.wikipedia.org/wiki/Locational_marginal_pricing): Locational marginal price.
- [**nMAE**](https://en.wikipedia.org/wiki/Mean_absolute_error): Normalized mean absolute error.
- [**Oversubscription**](https://lizhouyu.github.io/technical_posts/posts/power-oversubscription-brief/): Contracting or operating more IT load than the upstream path can supply at coincident peak.
- [**PCC**](https://en.wikipedia.org/wiki/Point_of_common_coupling): Point of common coupling.
- [**PUE**](https://en.wikipedia.org/wiki/Power_usage_effectiveness): Power usage effectiveness.
- [**QSA**](https://www.ercot.com/files/docs/2026/11/18/4.-BZ-VRT-Review-and-Next-Steps_Nov2026-LLWG.pdf): Quarterly Stability Assessment, which ERCOT treats as a prerequisite for Initial Energization.
- [**Ride-through**](https://lizhouyu.github.io/technical_posts/posts/caiso-20mw-pjm-fast-energization-gfm-halls/): Remaining connected through a grid fault or voltage sag.
- [**TDP**](https://en.wikipedia.org/wiki/Thermal_design_power): Thermal design power.
- [**TERL**](https://arxiv.org/abs/2611.26527): Thermal-guided ensemble reinforcement learning, the forecasting method in arXiv 2611.26527.
- [**UPS**](https://en.wikipedia.org/wiki/Uninterruptible_power_supply): Uninterruptible power supply.
- [**VRT**](https://en.wikipedia.org/wiki/Fault_ride_through): Voltage ride-through.

---

_How useful was today’s brief? Reply in Grok Bot chat with an overall rating (1–5) and, if you like, per-item ratings (1–5)._
