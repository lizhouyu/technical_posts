---
title: "Vertiv dates 800 VDC; inference fills checkpoint dips; who pays for the grid"
date: 2026-11-11 08:30:00 +0800
categories: [Daily Brief, Power]
tags: [800vdc, ramp-smoothing, ride-through, grid, power-capping, inference, training, carbon, industry, academia, adjacent]
description: "Vertiv expects 800 VDC sidecar hybrids from 2H 2027 and fully native 800 VDC halls from 2H 2028, and says the UPS now also protects the grid from the load. Infineon guides data-center power revenue to close to €4 B in FY27, up from €2.2 B. SoftBank books a USD 3.7 B loss after changing its plans for buying power-generation equipment. NC State and M.C. Dean fill training-checkpoint power dips with inference, cutting frequency deviation by 42–62%. Dartmouth releases an open-source multi-fidelity EMT model of data-center loads. A spot market for inference turns a power cap into a price. A directional carbon signal is proposed for data-center ramps on PJM, and a Nature Energy study asks who pays for the grid buildout."
media_subpath: /assets/img/briefs/2026-11-11/
image:
  path: fig-checkpoint-schematic.png
  alt: Illustrative schematic of a 2 MW, 120 second training-checkpoint power dip being filled by launched inference work
math: true
---

## At a glance

On Nov 10, [Vertiv](https://www.vertiv.com/en-us/ "Vertiv: US maker of data-center power (UPS, switchgear, busway) and cooling equipment.") put dates on the move to 800 VDC. Hybrid [sidecars](https://lizhouyu.github.io/technical_posts/posts/800v-dc-goes-live-calibrated-decode-caps/ "Sidecar: a power rack next to the IT racks that converts facility AC to 800 VDC near the load; covered in the Nov 4 brief.") that convert to 800 VDC next to the IT load start in **2H 2027**. Fully native end-to-end 800 VDC follows in **2H 2028**. In a sponsored [DCD](https://www.datacenterdynamics.com/ "DatacenterDynamics: data-center industry news and events publisher.") piece the same day, Vertiv engineers said that "the UPS protected the load from the grid … now it also protects the grid from the load," and that grid operators increasingly ask for [EMT](https://en.wikipedia.org/wiki/EMTP "Electromagnetic-transient simulation: time-domain modeling at microsecond resolution that captures converter and control dynamics.") models of whole facilities.

Two other Nov 10 numbers show how much money is moving through the power chain:

- [Infineon](https://www.infineon.com/ "Infineon Technologies: German power-semiconductor maker (Si, SiC, GaN) supplying PSUs, BBUs and 800 VDC converters.") guides data-center power revenue to **close to €4 B** for FY27, up from **€2.2 B** in FY26. It puts its AI power content at **USD 175 per kW** on average today.
- [SoftBank](https://group.softbank/en "SoftBank Group: Japanese investment group building US AI data centers with OpenAI (Stargate).") booked a **USD 3.7 B** loss after changing its plans for buying power-generation equipment for its US AI campuses.

Ramp smoothing gets a new lever from a fresh paper: fill a training [checkpoint](https://en.wikipedia.org/wiki/Application_checkpointing "Checkpointing: periodically saving model state so training can restart after a failure; GPUs mostly idle while it happens.")'s power dip with inference work that was going to run anyway. In simulation this cuts frequency deviation by **42–62%** and the battery's charging energy by **90–100%**. Two more papers turn a power cap into a price, and model the facility as the grid sees it. The adjacent slice asks what a ramp emits and who pays for the wires.

> Mix: 4 industry / 3 academia / 2 adjacent (~44/33/22%). arXiv's Nov 10 announcement (submissions through Nov 9) was the newest listing at scan time. All items below are new to this site.
{: .prompt-tip }

## Key developments

### 1. Vertiv puts dates on 800 VDC: sidecar hybrids in 2H 2027, native end-to-end in 2H 2028 · Nov 10 2026 · industry / rack-to-facility power

At the Baird Global Industrial Conference, Vertiv CEO Gio Albertazzi said the company still sees a spectrum of power architectures. At one end is traditional low-voltage AC; at the other is "an entire 800 VDC native end-to-end type of infrastructure." On timing: "2027, second half of 2027, is when we will start to have sidecars. That hybrid infrastructure that converts to 800 VDC in proximity of the IT load, and probably it will be the second half of 2028 when you will start to see end-to-end full 800 VDC. The key is the load."

He tied the choice to the job the building has to do. A [colocation](https://en.wikipedia.org/wiki/Colocation_centre "Colocation: a data center that rents space, power and cooling to many tenants, usually designed for long, flexible lifetimes.") site that needs "20 years of flexible resilience" stays closer to AC. A focused AI factory "on [Vera Rubin](https://nvidianews.nvidia.com/news/nvidia-vera-rubin-platform "NVIDIA Vera Rubin: NVIDIA's GPU/CPU platform after Blackwell, designed around 800 VDC rack power.") and above" would be native 800 VDC. Vertiv also described its UtilityInnovation Group acquisition as a way into [behind-the-meter](https://en.wikipedia.org/wiki/Distributed_generation "Behind the meter: generation or storage on the customer side of the utility meter, inside the facility fence.") generation and "orchestration with the grid," which it called highly site-specific.

**Caveats.** These are remarks at an investor conference, relayed in an AI-assisted transcript published by Investing.com. They are a roadmap, not shipment commitments.

**Implication.** For the next 18–24 months, most new AI halls will still have an AC front end with 800 VDC only at the row. That means the rack-level power-capping and smoothing stack (PSU shelves, [BBUs](https://www.opencompute.org/ "Battery backup unit: rack-level battery shelf (OCP Open Rack) that rides through short outages and can buffer load swings."), GPU caps) remains the main place where swings are handled until native DC buses with facility storage arrive in 2028.

- [Investing.com: Vertiv at Baird 2026 Global Industrial Conference, summary and full transcript (Nov 10 2026)](https://www.investing.com/news/transcripts/vertiv-at-baird-2026-global-industrial-conference-ai-demand-stays-strong-93CH-5015962)

### 2. "Now it also protects the grid from the load": Vertiv on ride-through and EMT models · Nov 10 2026 · industry (sponsored) / grid interaction

In a sponsored DCD MarketWatch article, Vertiv's Chris Thompson (VP, global microgrids) and Arturo Di Filippi (large power) argue that [fault ride-through](https://en.wikipedia.org/wiki/Fault_ride_through "Ride-through: staying connected and operating through a short grid voltage or frequency disturbance instead of tripping offline.") has moved from a niche topic to a core architecture decision. When a campus draws hundreds of MW, tripping offline during a disturbance turns a local protection action into a frequency event for the grid.

Three points stand out:

- **UPS role.** "We used to say the UPS protected the load from the grid … Now it also protects the grid from the load." The article adds that not every [UPS](https://en.wikipedia.org/wiki/Uninterruptible_power_supply "Uninterruptible power supply: batteries plus power electronics that carry IT load through grid disturbances.") provides grid-support functions.
- **Modeling.** Grid operators increasingly ask for EMT models built in [PSCAD](https://www.pscad.com/ "PSCAD/EMTDC: commercial electromagnetic-transient simulation software widely used for power-electronic and grid studies.") that cover the full chain: utility connection, switchgear, UPS, batteries, generators and IT load.
- **Coordination.** Cooling motors, pumps and [VFDs](https://en.wikipedia.org/wiki/Variable-frequency_drive "Variable-frequency drive: power electronics that run a motor at adjustable speed.") respond differently to sags. "The challenge is increasingly about control and coordination rather than hardware capability."

**Caveats.** This is sponsored vendor content with no data. Its claim that existing equipment "may already possess much of the technical resilience" needed is untested.

**Implication.** The same UPS that rides through a fault can shape how the load looks at the [point of interconnection](https://en.wikipedia.org/wiki/Point_of_common_coupling "Point of interconnection / common coupling: where a facility connects to the utility grid."). For ramp-smoothing research, that makes UPS control firmware a third place to act, next to GPU power caps and facility batteries. It also explains why open EMT models (item 6) matter.

- [DCD MarketWatch (sponsored by Vertiv): Too big to trip (Nov 10 2026)](https://www.datacenterdynamics.com/en/marketwatch/too-big-to-trip/)

### 3. Infineon: data-center power revenue heads for ~€4 B in FY27; AI power content about USD 175/kW · Nov 10 2026 · industry / PoL-to-rack supply chain

Infineon's Q4 FY2026 release forecasts FY27 revenue of about **€20 B**, with "revenue from power supplies for data centers … projected to reach close to €4 billion." The investor presentation breaks down FY26: **€2.2 B** of data-center revenue ("almost doubling vs. FY25"), of which **€1.7 B** was AI data center and **€0.5 B** classic data center. It puts "AI power content per kilowatt in the range of USD 100–250 growing further from USD 175/kW average today." Power & Sensor Systems revenue rose 25% quarter on quarter to **€1,796 M**, with AI servers and data centers the main growth driver.

**Caveats.** FY27 is guidance at an assumed EUR/USD of 1.15. "Content per kW" is Infineon's own metric. The presentation link below is a third-party mirror of the deck Infineon posted on its investor site.

**Implication.** Taken at face value, USD 175/kW is Infineon's own power-semiconductor content across the conversion chain, from facility rectifier to [point-of-load](https://en.wikipedia.org/wiki/Voltage_regulator_module "Point-of-load (PoL) converter: the final DC-DC stage next to the GPU or CPU that drops ~50 V or ~12 V to below 1 V.") converter. That is roughly **USD 175k** of Infineon-addressable power silicon per MW of rack power, which is where the energy-storage PSU, BBU and active-buffer features this site follows have to fit.

![Infineon data-center power revenue FY26 vs FY27 guidance](fig-infineon-dc-revenue.png){: w="1440" h="552" }
_Figure 1. Data from Infineon's Q4 FY2026 press release and investor presentation (Nov 10 2026). FY27 is company guidance._

- [Infineon: Q4 FY2026 results and FY2027 outlook (Nov 10 2026)](https://www.infineon.com/press-release/2026/infpr202611-025)
- [Infineon Q4 FY2026 investor presentation (PDF, third-party mirror)](https://vipress.net/wp-content/uploads/2026/11/Infineon-FY-2026.pdf)

### 4. SoftBank books a USD 3.7 B loss after changing its plans for buying power-generation equipment · Nov 10 2026 · industry / behind-the-meter power

SoftBank reported a fiscal Q2 net loss of **¥1.12 T (~USD 7 B)**. CNBC reports that this includes a **¥597.2 B (~USD 3.7 B)** loss "due to changes in procurement plans for power generation equipment for AI data center projects in the U.S." Cumulative payments for such equipment, for projects like the PORTS-Pike Technology Campus in Pike County, Ohio, reached **USD 9.48 B** by end-September. A SoftBank executive said: "We made bridge investments in advance to secure power generation equipment in anticipation of shortage." Reuters adds that SoftBank expects rebates of up to **USD 2.1 B** on future purchases.

**Caveats.** SoftBank has not itemized the equipment. Per Reuters, the CFO said intense competition for power equipment led to buying before long-term specifications were finalized, and the chief accounting officer said the payments could not be refunded when orders were cancelled.

**Implication.** The Nov 10 brief covered six-year turbine lead times. This is the other side of that story: early equipment bets can lose value when site plans change. Equipment size is set by peak power plus step tolerance. Capping and smoothing that lower the required peak, or make smaller units acceptable, reduce how much of this risk an operator has to carry.

- [CNBC: SoftBank swings to USD 7 billion loss after U.S. data center hit (Nov 10 2026)](https://www.cnbc.com/2026/11/10/softbank-2q-earnings-tech-selloff.html)
- [Reuters via StreetInsider: SoftBank books USD 7 billion quarterly loss on US data centre hit (Nov 10 2026)](https://www.streetinsider.com/Reuters/SoftBank+books+%247+billion+quarterly+loss+on+US+data+centre+hit%2C+financing+costs/27317116.html)

### 5. Filling training-checkpoint dips with inference work · arXiv Nov 9 2026 · academia / ramp smoothing (training + inference)

Ma, Sheng, … Lu ([NC State](https://www.ncsu.edu/ "North Carolina State University.")) and [M.C. Dean](https://www.mcdean.com/ "M.C. Dean: US electrical design-build firm for data centers and critical facilities; co-sponsor of this work.") start from a simple observation. Synchronous training checkpoints cause sharp, *predictable* power dips. They then schedule flexible inference work to fill those dips. A two-layer controller works as follows:

1. The **upper layer** picks which inference tasks to launch, and when, using launch-aligned GPU power templates and the expected checkpoint deficit.
2. The **lower layer** adjusts batch sizes of newly launched tasks online to correct tracking error.
3. **Early launching** smooths the onset of the dip, and **staged retirement** smooths the recovery.

The testbed is a [PSCAD/EMTDC](https://www.pscad.com/ "PSCAD/EMTDC: commercial electromagnetic-transient simulation software.") model of a 60 Hz islanded microgrid: a 50 MVA synchronous generator (inertia 6 s), PV, a ±5 MW droop-controlled [BESS](https://en.wikipedia.org/wiki/Battery_energy_storage_system "Battery energy storage system: grid-connected batteries plus inverters.") and a 50 MW data center with 16,304 schedulable inference GPUs. Power templates come from `nvidia-smi` traces on an [H100](https://www.nvidia.com/en-us/data-center/h100/ "NVIDIA H100: Hopper-generation data-center GPU, up to 700 W in SXM form.") running [GPT-OSS-20B](https://huggingface.co/openai/gpt-oss-20b "gpt-oss-20b: OpenAI's open-weight 21B-parameter mixture-of-experts language model."). Checkpoint drops of **1–3 MW** lasting 90–150 s give:

- **41.6–61.6%** lower maximum and **68.5–89.6%** lower mean absolute frequency deviation, compared with no scheduling.
- **65.1–100%** lower BESS peak charging power and **89.7–100%** lower charging energy.
- Better results than greedy scheduling when GPU resources are relatively abundant.

The authors report the costs too. Staged retirement terminates **3.5–4.8%** of requests. Pushing concurrency to batch 32 raises mean completion time by **121%** (HotpotQA) and **199%** (MATH-500) compared with batch 2.

**Caveats.** This is a simulation with a 50 MW islanded microgrid. Request arrivals are not dynamic, and the inference power templates come from a single GPU type.

**Implication.** This is the inverse of [GB300](https://developer.nvidia.com/blog/how-new-gb300-nvl72-features-provide-steady-power-for-ai/ "NVIDIA GB300 NVL72 power smoothing: energy storage in the power shelves, a power floor, and a 'power burner' on ramp-down.")'s "power burner," which wastes energy on purpose to hold the floor during a dip. Here the floor is held with useful tokens. It needs co-located training and deferrable inference with a known checkpoint schedule, which is the mixed fleet most large operators run. See the Spotlight for sizing.

![Checkpoint-aware inference scheduling results](fig-checkpoint-fill.png){: w="1440" h="552" }
_Figure 2. Ranges from the arXiv 2611.12621 abstract across checkpoint-drop sets A–C (1, 2 and 3 MW reference drops)._

- [arXiv 2611.12621: Reshaping Checkpoint-Induced Power Variations Through Inference Workload Scheduling](https://arxiv.org/abs/2611.12621)

### 6. Dartmouth releases an open-source, multi-fidelity EMT model of data-center loads · arXiv Nov 6 2026 · academia / grid interaction

Zhao, Tang and Zhao ([Dartmouth](https://engineering.dartmouth.edu/ "Thayer School of Engineering at Dartmouth College.")) built a modular PSCAD model of a data center. It has three parts: UPS-fed computing loads (UPS → PSU with [PFC](https://en.wikipedia.org/wiki/Power_factor#Power_factor_correction "Power-factor correction: the PSU front-end stage that draws sinusoidal current from the AC line.") and buck stages), VFD-driven cooling, and static lighting. Each converter comes at three fidelity levels:

- a switching model (2 µs time step);
- an average-converter model (10 µs);
- a reduced-order model, which runs **twice as fast** as the average model.

The paper gives a systematic way to tune controllers from target closed-loop bandwidths and damping ratios. Ride-through logic transfers the UPS to battery when the voltage leaves the ride-through envelope (0.2 s delay), then restores grid draw "subject to the specified power ramp limit." The paper cites the events that motivate it: 14.7 Hz oscillations near a Virginia data center, 1 Hz forced oscillations in the Midwest, 23 Hz in [ERCOT](https://www.ercot.com/ "Electric Reliability Council of Texas: grid operator for most of Texas."), and the 3.8 GW load transfer after a July 2026 [Dominion](https://www.dominionenergy.com/ "Dominion Energy: utility serving northern Virginia's Data Center Alley.") fault. The model is on GitHub.

**Caveats.** There is no experimental validation yet (the authors list it as future work). The three fidelities agree closely in simulation, though the switching model shows slightly higher steady-state power.

**Implication.** Item 2 says grid operators want full-chain EMT models. This one is open, so a power-capping or ramp-limiting controller can be closed around a realistic UPS and PSU chain and tested against ride-through envelopes, not just a power trace.

- [arXiv 2611.10179: Open-Source Multi-Fidelity EMT Modeling of Data Center Loads for Power System Studies](https://arxiv.org/abs/2611.10179)
- [GitHub: Generic-EMT-Modeling-of-Data-Center-Load](https://github.com/xingyuz-phd/Generic-EMT-Modeling-of-Data-Center-Load)

### 7. Spot markets for inference: a power cap becomes a price · arXiv Nov 8 2026 · academia / inference capping

Quanyan Zhu models an inference provider that serves several models on a shared fleet **under a power cap**. Each model is sold in two tiers: an interactive tier with a speed promise, and a spot tier for preemptible work with a deadline. Two results stand out. One interactive token displaces a fixed number $$\rho_m > 1$$ of spot tokens. The optimal spot price sits midway between the interactive price and the effective cost of capacity in the deadline window, which is close to today's half-price batch tier only when the fleet is slack. A linear-program [MPC](https://en.wikipedia.org/wiki/Model_predictive_control "Model predictive control: repeatedly solving a short-horizon optimization and applying the first step.") solves in about **7 ms** per period.

The test is a simulated week on a 512-accelerator fleet. On Friday, a [demand-response](https://en.wikipedia.org/wiki/Demand_response "Demand response: a customer cutting or shifting load when the grid operator asks, usually for payment.") event caps the facility at 62% of nominal (**236 kW**) for 2 hours, announced 2 hours ahead. The controller raises spot prices, works down the backlog early, and unloads replicas (500 → 322 loaded accelerators), so facility power falls by **111 kW**. Interactive traffic is served in full; the spot tier absorbs the curtailment. Fixed half-price practice loses interactive tokens instead. Over the week, profit rises **7.4%**, capturing **93%** of the perfect-forecast gain.

**Caveats.** This is a single-author model with a simulated fleet, and it does not model GPU-level power dynamics.

**Implication.** This is the economic version of the 11-05 query-routing knob. Deferrable inference is the flexible load, and the spot price tells buyers when the facility is curtailed. It pairs naturally with item 5: the same spot pool can fill checkpoint dips in seconds and absorb DR caps over hours.

- [arXiv 2611.11215: Spot Markets for AI Inference: Dynamic Capacity Allocation and Pricing on a Shared Accelerator Fleet](https://arxiv.org/abs/2611.11215)

### 8. One number per hour is not enough: directional carbon intensity of data-center ramps on PJM · arXiv Nov 9 2026 · adjacent / carbon-aware ramps

Shi and Yan compute a **directional carbon intensity**: the emission caused or avoided per MWh of a *finite* upward or downward ramp. They do this for every hour of 2025 on the [PJM](https://www.pjm.com/ "PJM Interconnection: regional grid operator for 13 eastern US states and DC.") fossil fleet and compare it with the [locational marginal emission rate](https://en.wikipedia.org/wiki/Emission_intensity "Marginal emission rate: emissions from the generator that responds to a small change in load at a location.") (LME) and the regional average. Three findings:

- The LME misstates a **1 GW** ramp by more than **10%** in **60–83%** of hours, in eleven of twelve months.
- Upward and downward ramps differ in a quarter to three quarters of hours, but agree on their monthly mean.
- Location-based reporting assigns **47–59%** of a ramp's emission to other consumers.

Code and derived results are on Zenodo.

**Caveats.** The analysis covers PJM's fossil fleet only, for 2025. It is a dispatch-model estimate, not metered emissions.

**Implication.** Carbon-aware capping and load shifting should use a signal sized to the ramp it actually makes. A campus that ramps hundreds of MW at once (job starts, DR events) is not a marginal load.

- [arXiv 2611.12056: One number per hour is not enough: directional carbon intensity of data-center ramps on the PJM fleet](https://arxiv.org/abs/2611.12056)
- [Zenodo: code and derived results](https://doi.org/10.5281/zenodo.24074188)

### 9. Nature Energy: data centers raise wholesale prices and shift grid costs onto households · Nov 9 2026 · adjacent / grid economics

Cheng Feng and Fengqi You ([Cornell](https://www.cornell.edu/ "Cornell University, Ithaca, New York.")) combine causal analysis of price records with transmission plans and cost-allocation dockets across four major US grids for 2020–2025. They find:

- Cumulative wholesale price increases attributable to data centers exceed **10%** in the most exposed hubs by 2025. Cornell's release cites **15%** in Virginia and **20%** in the southern Bay Area.
- In regulated tariffs, residential users are allocated a median **47%** of costs "despite contributing far less to demand growth."
- Rural communities bear burden increases **76%** larger than urban ones, and the lowest-income households face extra energy burdens of up to **28 percentage points**.

Per Cornell, data centers paid **USD 3.12 B** of the **USD 8.25 B** in 2025 infrastructure costs linked to their growth, and transmission investment rose from **USD 2 B (2020)** to **USD 34 B (2025)**.

**Caveats.** The full paper is paywalled, and we read the abstract and Cornell's release. Attributing price effects depends on the counterfactual model.

**Implication.** This is the political driver behind the "bring your own capacity or accept curtailment" bargains covered in earlier briefs. Every MW that capping and flexibility take off the coincident peak is a MW of transmission that households don't fund.

- [Nature Energy: Data centres asymmetrically exacerbate energy burdens through wholesale price increases and regressive grid cost shifting](https://www.nature.com/articles/s41560-026-02163-x)
- [Cornell Chronicle: Data centers need power – lower income, rural residents pay the price (Nov 2026)](https://news.cornell.edu/stories/2026/11/data-centers-need-power-lower-income-rural-residents-pay-price)

## Spotlight: sizing an inference "fill" for a checkpoint dip

Let a synchronous checkpoint drop training power by $$\Delta P_{ck}$$ for $$T_{ck}$$ seconds. Without a fill, a battery holding the grid draw flat must **absorb**

$$
E_{b} = \Delta P_{ck}\, T_{ck},
$$

which is about **25 / 67 / 125 kWh** for the paper's reference drops of 1 MW / 90 s, 2 MW / 120 s and 3 MW / 150 s. The battery must do this every checkpoint, at a peak charging power of $$\Delta P_{ck}$$. An inference fill instead needs roughly

$$
N_{GPU} \approx \frac{\Delta P_{ck}}{\bar p_{inc}}
$$

accelerators of deferrable work ready to launch, where $$\bar p_{inc}$$ is the incremental power one inference task adds over a lightly loaded GPU. As a **hypothetical** example, $$\bar p_{inc} = 200$$ W gives 10,000 GPUs for a 2 MW dip. That fits within the paper's 16,304-GPU pool, and it explains why the gain over greedy scheduling depends on how plentiful GPU resources are. The fill has to rise and fall at the same speed as the dip's edges. That is what early launching and staged retirement do, at a cost of 3.5–4.8% terminated requests.

![Illustrative checkpoint fill schematic](fig-checkpoint-schematic.png){: w="1440" h="552" }
_Figure 3. **Illustrative schematic, not results.** The dip shape uses the paper's scenario-B reference values (2 MW, 120 s, 2 s linear ramps, 50 MW target); the fill level is drawn for illustration._

## Bottom line

The 800 VDC roadmap now has dates: hybrids in 2H 2027, native halls in 2H 2028. Until then, the AC-fronted rack and UPS layers carry most of the smoothing load, and vendors are recasting the UPS as a grid-facing device. The money is moving in step, with about USD 175/kW of power silicon and multi-billion bets on generation that do not always pay off. On the research side, the best idea today is a scheduling one: predictable training dips can be filled with deferrable inference instead of battery cycles or wasted energy. The same spot-tier inference pool can also absorb hours-long DR caps (item 7). Carbon and cost studies add a reason to care: ramps are not marginal, and households are paying for the peak.

## Glossary

- [**800 VDC**](https://nvidianews.nvidia.com/news/nvidia-vera-rubin-platform): Rack and facility DC distribution at 800 V (NVIDIA Vera Rubin era).
- [**BBU**](https://www.opencompute.org/): Rack battery backup unit.
- [**Behind the meter**](https://en.wikipedia.org/wiki/Distributed_generation): On the customer side of the utility meter.
- [**BESS**](https://en.wikipedia.org/wiki/Battery_energy_storage_system): Battery energy storage system.
- [**Checkpointing**](https://en.wikipedia.org/wiki/Application_checkpointing): Periodically saving training state.
- [**Colocation**](https://en.wikipedia.org/wiki/Colocation_centre): A multi-tenant data center.
- [**Demand response**](https://en.wikipedia.org/wiki/Demand_response): Cutting load when the grid asks.
- [**EMT**](https://en.wikipedia.org/wiki/EMTP): Electromagnetic-transient simulation.
- [**Fault ride-through**](https://en.wikipedia.org/wiki/Fault_ride_through): Staying connected through grid disturbances.
- [**H100**](https://www.nvidia.com/en-us/data-center/h100/): NVIDIA Hopper data-center GPU.
- [**Infineon**](https://www.infineon.com/): German power-semiconductor maker.
- [**Marginal emission rate (LME)**](https://en.wikipedia.org/wiki/Emission_intensity): Emissions of the generator that responds to a small load change.
- [**MPC**](https://en.wikipedia.org/wiki/Model_predictive_control): Model predictive control.
- [**PFC**](https://en.wikipedia.org/wiki/Power_factor#Power_factor_correction): Power-factor correction stage in a PSU.
- [**PJM**](https://www.pjm.com/): Mid-Atlantic/Midwest grid operator.
- [**Point of interconnection**](https://en.wikipedia.org/wiki/Point_of_common_coupling): Where a facility meets the grid.
- [**Point-of-load (PoL)**](https://en.wikipedia.org/wiki/Voltage_regulator_module): Final DC-DC stage next to the chip.
- [**PSCAD/EMTDC**](https://www.pscad.com/): EMT simulation software.
- [**Sidecar**](https://lizhouyu.github.io/technical_posts/posts/800v-dc-goes-live-calibrated-decode-caps/): A power rack converting to 800 VDC next to the IT racks.
- [**SoftBank**](https://group.softbank/en): Japanese investment group building US AI campuses.
- [**UPS**](https://en.wikipedia.org/wiki/Uninterruptible_power_supply): Uninterruptible power supply.
- [**Vera Rubin**](https://nvidianews.nvidia.com/news/nvidia-vera-rubin-platform): NVIDIA's post-Blackwell platform.
- [**Vertiv**](https://www.vertiv.com/en-us/): Data-center power and cooling vendor.
- [**VFD**](https://en.wikipedia.org/wiki/Variable-frequency_drive): Variable-frequency drive.

---

_How useful was today's brief? Reply in Grok Bot chat with an overall rating (1–5) and, if you like, per-item ratings (1–9)._
