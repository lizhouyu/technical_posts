---
title: "Grid-forming smoothing PCS; MISO's 30 MW/min ramp; carbon-optimal caps"
date: 2026-11-10 08:30:00 +0800
categories: [Daily Brief, Power]
tags: [ramp-smoothing, grid, 800vdc, sst, energy-storage, ride-through, power-capping, inference, industry, academia, adjacent]
description: "Power Electronics unveils AIPCS, a power-conversion platform that smooths AI load swings in under 5 ms (under 3 ms in grid-forming mode) and feeds 800 VDC directly from medium voltage. Enphase is now building 5.5 kW IQ SST modules in Texas. MISO's proposed 30 MW/min ramp limit still awaits FERC. Turbine lead times push data centers to used and aeroderivative units. PNNL sizes one battery for demand response, smoothing and voltage support. A 448-GPU forecasting benchmark shows ramp-aware scenarios cut reserve cost by 7–11%. Two papers address ride-through. EPFL finds the carbon-optimal H100 cap is 500 W, not the 450 W energy optimum."
media_subpath: /assets/img/briefs/2026-11-10/
image:
  path: fig-ramp-limit-bess.png
  alt: Illustrative schematic of a 100 MW load step held to a 30 MW per minute grid ramp, with a battery covering the gap
math: true
---

## At a glance

Ramp smoothing is turning into a product line. On Nov 9, Spanish inverter maker [Power Electronics](https://www.power-electronics.com/ "Power Electronics: Spanish maker of utility-scale solar inverters, battery power-conversion systems and EV chargers, now selling AI data-center power platforms.") announced its **AIPCS** platform. FreePuls smooths what AI loads draw from the grid with a claimed response time **under 5 ms**. FreePuls EVO is a [grid-forming](https://en.wikipedia.org/wiki/Grid-forming_inverter "Grid-forming inverter: an inverter that sets its own voltage and frequency like a synchronous generator, instead of following the grid's.") version that responds in **under 3 ms**. A third option feeds **800 VDC** directly from medium voltage. The same day, [Enphase](https://enphaseenergy.gcs-web.com/news-releases/news-release-details/enphase-advances-iq-solid-state-transformer-development-ai-data/ "Enphase Energy: US maker of solar microinverters and home batteries, now developing a solid-state transformer for AI data centers.") said it is building **5.5 kW** power modules for its IQ [solid-state transformer](https://en.wikipedia.org/wiki/Solid-state_transformer "Solid-state transformer (SST): a transformer built from high-frequency power electronics instead of a large 50/60 Hz iron core; it can convert medium-voltage AC directly to DC.") in Texas.

On the grid side, [MISO](https://www.misoenergy.org/ "Midcontinent Independent System Operator: grid operator for 15 central US states and Manitoba.")'s proposed **30 MW/min** ramp limit for computational loads is still waiting on [FERC](https://www.ferc.gov/ "Federal Energy Regulatory Commission: US regulator of interstate transmission and wholesale power markets."). Reuters reports that gas-turbine lead times of about **six years** are pushing AI campuses toward used, refurbished and jet-engine-derived units.

Four papers cover ramp smoothing and grid interaction:

- [PNNL](https://www.pnnl.gov/ "Pacific Northwest National Laboratory: US Department of Energy national lab with a large grid-research program.") sizes one battery to cover demand response, fast smoothing and voltage support.
- A 448-GPU forecasting benchmark shows that keeping ramps realistic in load scenarios cuts reserve cost by **7.4–10.6%**.
- Two groups model and control [ride-through](https://en.wikipedia.org/wiki/Fault_ride_through "Ride-through: staying connected and operating through a short grid voltage or frequency disturbance instead of tripping offline.") so data centers stop dropping off the grid during faults.

Two adjacent papers round out the brief. EPFL's Green500 campaign finds that the **carbon-optimal** H100 power cap is **500 W**, not the **450 W** energy optimum. A calibrated model of [LLM](https://en.wikipedia.org/wiki/Large_language_model "Large language model: a neural network trained on large text corpora, served by generating one token at a time.") serving ranks deployment designs by SLO goodput per kW.

> Mix: 4 industry / 3 academia / 2 adjacent (~44/33/22%). arXiv's Nov 9 announcement (submissions through Nov 6) was the newest listing at scan time. All arXiv items below are new to this site.
{: .prompt-tip }

## Key developments

### 1. Power Electronics AIPCS: grid-forming load smoothing under 3 ms, plus MV-to-800 VDC · Nov 9 2026 · industry / ramp smoothing

Power Electronics will present AIPCS at [RE+ 2026](https://www.re-plus.com/ "RE+: North America's largest clean-energy trade show, held in Las Vegas Nov 17–19 2026.") (Las Vegas, Nov 17–19) in three configurations:

- **FreePuls** is a grid-following unit that "smooths the power that AI loads draw from the grid," with a "proven response time of less than 5 ms."
- **FreePuls EVO** adds patent-pending, self-tuning grid-forming controls (AGFLS). The company says the equivalent response time is **under 3 ms** on both strong and weak grids, with a seamless transition to islanded operation.
- **FreeQon** isolates critical loads from grid disturbances.
- **AIPCS 800PS** converts medium voltage directly to 800 VDC.

An AIPCS Controller coordinates power management and "near-instantaneous load compensation." The company says it has more than **10 GW** of US data-center projects in progress and plans a Houston factory with **40 GW/yr** of capacity.

**Caveats.** These are vendor claims in a launch announcement. There is no datasheet, no energy or power rating for the buffer, and no independent test. "Response time" is not defined, for example whether it means time to first current change or time to settle.

**Implication.** A few milliseconds is fast enough to act inside a GPU training iteration's compute-to-communication swing, which [GB300](https://developer.nvidia.com/blog/how-new-gb300-nvl72-features-provide-steady-power-for-ai/ "NVIDIA GB300 NVL72 power smoothing: energy storage in the power shelves, a power floor, and a 'power burner' on ramp-down.")-class rack storage targets at the shelf. It is also well inside ERCOT's draft 5 s window and MISO's per-minute limit (item 3). Grid-forming storage at the facility edge is a second place, next to rack-level power capping and smoothing, to meet a ramp rule. The open question is cost per MW of smoothing versus giving up compute through caps.

- [Power Electronics: AIPCS platform announcement (Nov 9 2026)](https://www.power-electronics.com/en/blog/2026/power-electronics-reinforces-leadership-ai-data-center-power-infrastructure-aipcs-re-plus-2026)

### 2. Enphase starts building 5.5 kW IQ SST modules in Texas; full-system demos due this month · Nov 9 2026 · industry / facility-to-rack power

Enphase's Nov 9 release says it has started building power modules for its IQ Solid-State Transformer in Arlington, Texas. It is using them to assemble and validate full-scale racks. Each module is rated **5.5 kW**, and hundreds of them make up a rack of **up to 5 MW** that converts medium-voltage AC directly to **800 VDC**. The modules share a form factor and production line with Enphase's microinverters.

Enphase's Sept 8 release described the same program with a **4 kW** module. It claimed "sub-millisecond response to dynamic AI loads, helping reduce the need for local battery energy buffering near AI compute racks." It listed validation at **13.8–34.5 kV**, [GaN](https://en.wikipedia.org/wiki/Gallium_nitride "Gallium nitride: a wide-bandgap semiconductor that switches faster and with lower loss than silicon.") switching, and a custom control ASIC, with **full-system demonstrations expected in November 2026** and customer pilots in 2027.

**Caveats.** The module rating changed from 4 kW to 5.5 kW between the two releases. The response-time and battery-reduction claims are forward-looking, and no efficiency number has been published.

**Implication.** SSTs come up in every brief (Envision, Eaton, now Enphase and Power Electronics' 800PS). The claim worth testing is whether a fast SST can replace part of the rack battery. An SST can shape how fast power is pulled from the grid, but it stores almost no energy. The step energy still has to come from somewhere (see the Spotlight).

- [Enphase: 8M+ microinverters shipped; IQ SST modules in production (Nov 9 2026)](https://www.globenewswire.com/news-release/2026/11/09/3398358/0/en/enphase-energy-announces-more-than-8-million-iq-microinverters-and-nearly-500-mwh-of-iq-batteries-have-shipped-from-u-s-manufacturing-facilities.html)
- [Enphase: IQ SST power modules now being built in Texas (Sept 8 2026)](https://enphaseenergy.gcs-web.com/news-releases/news-release-details/enphase-advances-iq-solid-state-transformer-development-ai-data/)

### 3. MISO's proposed 30 MW/min ramp limit for computational loads is still pending at FERC · Nov 7 2026 status · industry / grid rules

A Nov 7 review of FERC docket **ER26-3650** by DistroForge, a utility-procurement research site, summarizes what MISO asked for on Aug 28. A **Computational Load** is a Large Load (≥ 50 MW at one substation) with ≥ 25 MW of IT equipment. For these loads, MISO proposes:

- [PMUs](https://en.wikipedia.org/wiki/Phasor_measurement_unit "Phasor measurement unit: a high-rate, GPS-time-stamped grid sensor.") installed by the transmission owner at the customer's expense.
- Ride-through performance.
- Initial up- and down-ramp limits of **30 MW per minute**, measured in aggregate across the load's withdrawal points. "Eligible generation or other resources" may provide the ramp smoothing.

The requested effective date is **Dec 4 2026**. As of Nov 7, FERC had not ruled. The detailed ride-through criteria sit in a technical compendium, not in the tariff.

Elsewhere, [PJM](https://www.pjm.com/ "PJM Interconnection: regional grid operator for 13 eastern US states and DC.")'s ride-through timeline schedules "Develop & Establish LCL Ramp-Rate" for **Q1 2027**. [CAISO](https://www.caiso.com/ "California Independent System Operator: grid operator for most of California.") will file its large-load response to FERC's June [show-cause order](https://insidelines.pjm.com/reliability-standards-to-manage-large-load-disconnection-events-proposed-by-pjm/ "FERC's June 18 2026 Section 206 order asking RTOs whether their tariffs adequately address large-load ramp rates and ride-through.") by **Nov 16**. That filing includes a "flexible interim load interconnection."

**Caveats.** DistroForge is a secondary summary of the filing, and 30 MW/min is a proposed starting value that the manual can change per load.

**Implication.** 30 MW/min is a slow, minute-scale limit compared with ERCOT's 10 MW / 5 s oscillation draft. It is aimed at job starts, stops and restarts, not per-iteration swings. For a 300 MW campus, a full ramp from idle would take **10 minutes**. That is something a job scheduler and power-cap ramps can do on their own, or a battery can cover (Spotlight).

- [DistroForge: MISO large load requirements, ER26-3650 (Nov 7 2026)](https://distroforge.com/blog/miso-large-load-requirements-ferc-filing/)
- [PJM Planning Committee: LCL ride-through requirements and timeline (Sept 8 2026, PDF)](https://www.pjm.com/-/media/DotCom/committees-groups/committees/pc/2026/20260908/20260908-item-05---1-large-load-ride-through---presentation.pdf)
- [CAISO Board advances large-load procedures (Oct 28 2026)](https://www.caiso.com/about/news/news-releases/caiso-board-advances-new-procedures-for-connecting-large-loads-quickly-and-reliably)

### 4. Turbine scarcity: used units, jet-engine gensets and SpaceX's $24 B Starbase gas-plus-compute plan · Nov 9 2026 · industry / behind-the-meter power

A Nov 9 Reuters analysis quotes [Wood Mackenzie](https://www.woodmac.com/ "Wood Mackenzie: energy research and consulting firm.") saying that US gas-turbine delivery conversations now center on **2030–31**, with average delivery taking about **six years**. Global orders top **100 GW** against **60–70 GW** of production capacity. In response, developers are buying used turbines (about **$1.3–1.7 M/MW**, versus **$2–2.5 M/MW** new) and [aeroderivative](https://en.wikipedia.org/wiki/Aeroderivative_gas_turbine "Aeroderivative gas turbine: a power-generation turbine adapted from a jet engine; smaller and faster to start than heavy-frame units.") units. An equipment supplier says some sites deploy **more than 100** small turbines and mix models and brands. [Wärtsilä](https://www.wartsila.com/ "Wärtsilä: Finnish maker of marine and power-plant reciprocating engines.") reports about **3 GW** of US data-center orders for gas engines.

A separate Reuters report the same day says [SpaceX](https://www.spacex.com/ "SpaceX: US launch company that acquired xAI in 2026.") has filed for a property-tax abatement on a roughly **$24 B** gas-fired power plant and "super-compute facility" at Starbase, Texas. The public hearing is set for Dec 9. The notice gives no generating capacity.

**Caveats.** Reuters is relaying broker and supplier quotes. The SpaceX project is at the abatement-application stage.

**Implication.** Fleets of many small, mixed-model generators have limited and uneven step-load tolerance, set by governor response and machine inertia. On these campuses, the GPU-side ramp and cap policy, plus a battery buffer, effectively becomes the generator protection scheme. (The Nov 9 brief already covered the Anthropic generator deal.)

- [Reuters via Investing.com: AI power rush sends data centres hunting for used turbines and jet engines (Nov 9 2026)](https://www.investing.com/news/stock-market-news/analysisai-power-rush-sends-data-centres-hunting-for-used-turbines-and-jet-engines-5010537)
- [Reuters via Investing.com: SpaceX plans $24 billion gas power plant, data center project in Texas (Nov 9 2026)](https://www.investing.com/news/stock-market-news/spacex-plans-24-billion-gas-power-plant-data-center-project-in-texas-5013083)

### 5. PNNL: size one battery for demand response, fast smoothing and voltage sag support · arXiv Nov 6 2026 · academia / ramp smoothing

Wang, Sharma and Ramachandran at PNNL co-optimize a [BESS](https://en.wikipedia.org/wiki/Battery_energy_storage_system "Battery energy storage system: grid-connected batteries plus inverters.")'s power rating and energy capacity. They split its capability across three interconnection-driven services:

1. Demand response over a fixed duration.
2. Reserved active power for high-magnitude, high-frequency load fluctuations, with zero net state-of-charge change.
3. Reactive power for voltage support at the [PCC](https://en.wikipedia.org/wiki/Point_of_common_coupling "Point of common coupling: where a facility connects to the utility grid.").

Minute-level scheduling enforces state-of-charge feasibility and load ramp limits. A controllable queue of delay-insensitive compute tasks adds flexibility.

The case study uses a real data-center load profile. Demand response mainly drives **energy** capacity, while voltage support drives a much higher **power** rating because of the reactive and apparent power it needs. In stress tests, frequent demand-response events during high-load periods leave too little time to recharge, which lowers the load reduction the battery can guarantee.

**Implication.** This is the planning-side twin of item 3: it turns a list of interconnection requirements into a MW and MWh specification. For capping research, the delay-insensitive queue is the hook. Each MW of credible, deferrable compute reduces the battery size needed.

- [arXiv 2611.09001: Supporting Data Center Grid Integration via Co-Optimized BESS Sizing and Capacity Allocation](https://arxiv.org/abs/2611.09001)

### 6. Forecasting AI-cluster load for the grid: calibrated marginals aren't enough, ramps matter · arXiv Nov 6 2026 · academia / grid interaction

Yao, Lin, Zhao, Yue and Wang (SMU, UT Arlington, [Brookhaven](https://www.bnl.gov/ "Brookhaven National Laboratory: US DOE national lab in New York.")) build an open benchmark from measured GPU power on a **448-GPU** cluster and evaluate forecasts in four stages, ending in reserve sizing.

After a rise in cluster utilization, a quantile [LightGBM](https://lightgbm.readthedocs.io/ "LightGBM: a gradient-boosted decision-tree library.") model's nominal 90% interval covered only **63.4%** of outcomes. Online regime-conditioned calibration brought coverage back to **87.3%**. Even with well-calibrated forecasts, sampling each time step independently produced unrealistic ramps and peaks and bought too much reserve. Rebuilding the time dependence from past forecast errors matched the ramp statistics and cut reserve cost by **7.4–10.6%**.

**Implication.** To a grid operator, an AI campus's ramp distribution is a cost item. Power caps and job-start throttles change exactly the statistics this benchmark scores. That makes it a ready way to put a dollar value on a capping policy.

- [arXiv 2611.08929: Grid-Oriented Probabilistic Load Forecasting for AI Data Centers](https://arxiv.org/abs/2611.08929)

### 7. Ride-through, two ways: grid-side reactive-power coordination and a 100 MW EMT facility model · arXiv Nov 5 2026 · academia / grid interaction

Two Nov 5 papers address the failure mode behind PJM's July event, when nearly **4,000 MW** of northern-Virginia data-center load unexpectedly disconnected and switched to backup generation.

- **Grid side.** Lu and Weng (Arizona State) build a ride-through-aware extension of quadratic voltage control. It scores voltage deviations against each facility's voltage–duration envelope when allocating limited reactive power. On the IEEE 14-bus system, it cuts the mean data-center disconnection rate by **44.8%** and lost grid demand by **27.4%** compared with the best baseline. They also test on the 39-bus and 140-bus systems.
- **Facility side.** Zheng, Maharjan et al. (Iowa State University, INS Engineering) present an [EMT](https://en.wikipedia.org/wiki/EMTP "Electromagnetic-transient simulation: time-domain modeling at microsecond resolution that captures converter and motor dynamics.") model of a **100 MW** data center. It includes a [UPS](https://en.wikipedia.org/wiki/Uninterruptible_power_supply "Uninterruptible power supply: batteries plus power electronics that carry IT load through grid disturbances.") with batteries, induction-motor cooling, a VFD-driven air handler, and an aggregated server load. A voltage-based state machine coordinates the UPS mode (eco, double conversion or battery), the air handler's supply path, and a **ramped reconnection** after the fault clears. Its voltage and active-power trajectories closely match the PSS/E PERC1 aggregate model, and it also resolves converter and motor-reacceleration transients.

**Implication.** The ramped reconnection is a ramp-smoothing problem in its own right. A 100 MW facility returning from UPS to grid all at once is the step that ramp rules try to forbid. Coordinating GPU power caps during the return window could shrink that step without a larger battery.

- [arXiv 2611.08777: Reducing Data-Center Load Transfers with Ride-Through-Aware Voltage Control](https://arxiv.org/abs/2611.08777)
- [arXiv 2611.08614: EMT Modeling and Coordinated Mode-Transition Ride-Through Control of Modern Data Centers](https://arxiv.org/abs/2611.08614)
- [PJM Inside Lines: proposed ride-through standards after the July 22 event](https://insidelines.pjm.com/reliability-standards-to-manage-large-load-disconnection-events-proposed-by-pjm/)

### 8. EPFL Green500: the energy-optimal H100 cap is 450 W, but the carbon-optimal cap is 500 W · arXiv Nov 6 2026 · adjacent / power capping & sustainable AI

EPFL's SCITAS and EcoCloud teams report two [Green500](https://top500.org/lists/green500/ "Green500: twice-yearly ranking of supercomputers by HPL energy efficiency (Gflop/s per watt).") measurement campaigns on the Kuma cluster: 80 nodes with 4× H100 SXM5 each, liquid-cooled GPUs, running [HPL](https://en.wikipedia.org/wiki/LINPACK_benchmarks "HPL (High-Performance Linpack): the dense linear-algebra benchmark behind Top500 and Green500.").

Energy efficiency peaks at a **450 W** per-GPU cap, which costs about **11%** in performance and saves about **20%** in energy. When the team adds embodied emissions with a life-cycle method (Swiss grid, 6-year lifetime), the **carbon** optimum moves to **500 W**. The optimum stays at 500 W under several sensitivity cases. Only at a grid carbon intensity of about **400 gCO₂e/kWh** does usage dominate. Along the way, the campaign found defective thermal pads on some H100s that were dragging HPL results down.

**Caveat.** This is a dense HPL workload, not LLM inference. The authors call for AI-like benchmarks.

**Implication.** The best cap depends on what you are optimizing (energy, carbon or throughput) and on the grid mix. In a carbon-aware oversubscription policy, embodied emissions argue for capping less on clean grids.

![Kuma GPU power cap vs HPL efficiency and performance](fig-kuma-powercap.png){: w="1440" h="552" }
_Figure 1. Data from arXiv 2611.09251, Tables 1–2: HPL on 80 H100 nodes. Level 2 used PDU measurements and Level 3 used revenue-grade power meters, so the absolute values differ between campaigns._

- [arXiv 2611.09251: Green500: Adventure in Qualifying a Cluster](https://arxiv.org/abs/2611.09251)

### 9. Should you split decode? Ranking LLM serving designs by SLO goodput per kW · arXiv Nov 5 2026 · adjacent / inference power budget

Ramyad Hadidi's SiliconForge is a calibrated model that compares prefill/decode disaggregation (P/D) with an extra attention/[FFN](https://en.wikipedia.org/wiki/Transformer_%28deep_learning_architecture%29 "Feed-forward network: the per-token MLP block in a transformer layer; attention-FFN disaggregation runs it on separate hardware.") split of decode (AFD). It covers four model directions, four accelerator classes and two fabrics, all under the **same power budget**. Neither design shows a robust deployment-level advantage in [SLO](https://en.wikipedia.org/wiki/Service-level_objective "Service-level objective: a latency or throughput target a serving system must meet.") goodput per kW. AFD's largest lead comes from fitting one more prefill replica into the budget. Re-optimizing mappings and pool sizes on fixed hardware cuts the median normalized goodput loss from early commitment from **36% to 9%**.

**Implication.** Treating goodput per kW as the objective is the right lens for power-capped inference halls. The finding that pool sizing matters more than the split suggests that power headroom is best spent on re-balancing pools rather than on a new architecture.

- [arXiv 2611.08299: Should You Split Decode? Disaggregation Across Future Models and Accelerators](https://arxiv.org/abs/2611.08299)

## Spotlight: what a ramp limit costs in battery

Hold grid draw to a ramp limit $R$ while the IT load steps up by $\Delta P$. The battery must supply the difference:

$$
P_b(t) = \Delta P - R\,t \quad \text{for } 0 \le t \le \frac{\Delta P}{R},
\qquad
E_b = \frac{\Delta P^2}{2R}.
$$

Take MISO's proposed $R = 30$ MW/min and an illustrative 100 MW job-start step. The battery needs **100 MW** of power for about **3.3 min** and roughly **2.8 MWh** of energy. The energy grows with the **square** of the step, so halving the step (staggered starts, or a cap ramp from 50%) cuts the energy to a quarter. The peak power falls by half. A fast SST or grid-forming PCS (items 1–2) can control the shape of the grid draw, but without storage behind it, the load itself has to follow $R$. In that case the power cap or scheduler is the battery.

![Illustrative ramp-limit schematic](fig-ramp-limit-bess.png){: w="1380" h="552" }
_Figure 2. **Illustrative schematic, not data.** It shows a hypothetical 100 MW step. Only the 30 MW/min value comes from MISO's proposed tariff (ER26-3650, pending)._

## Bottom line

Ramp limits are arriving at several timescales: ERCOT's draft works at seconds, MISO's proposal at minutes, and PJM's is due in 2027. Vendors are answering with millisecond-class grid-forming power-conversion systems and SSTs. Research is turning the requirements into battery MW/MWh specs, reserve costs and ride-through controllers. The common thread for capping research is that every MW of controllable GPU power (staggered starts, cap ramps, deferrable queues) substitutes for battery power and energy. The quadratic step-energy relationship makes the first few MW of shaping the most valuable.

## Glossary

- [**Aeroderivative turbine**](https://en.wikipedia.org/wiki/Aeroderivative_gas_turbine): A gas turbine adapted from a jet engine.
- [**BESS**](https://en.wikipedia.org/wiki/Battery_energy_storage_system): Battery energy storage system.
- [**CAISO**](https://www.caiso.com/): California's grid operator.
- [**EMT**](https://en.wikipedia.org/wiki/EMTP): Electromagnetic-transient simulation.
- [**Enphase**](https://enphaseenergy.gcs-web.com/news-releases/news-release-details/enphase-advances-iq-solid-state-transformer-development-ai-data/): Microinverter maker developing the IQ SST.
- [**FERC**](https://www.ferc.gov/): US federal energy regulator.
- [**GaN**](https://en.wikipedia.org/wiki/Gallium_nitride): Gallium nitride power semiconductors.
- [**GB300 power smoothing**](https://developer.nvidia.com/blog/how-new-gb300-nvl72-features-provide-steady-power-for-ai/): NVIDIA rack-level storage and power floor.
- [**Green500**](https://top500.org/lists/green500/): Supercomputer energy-efficiency ranking.
- [**Grid-forming (GFM)**](https://en.wikipedia.org/wiki/Grid-forming_inverter): An inverter that sets its own voltage and frequency.
- [**HPL**](https://en.wikipedia.org/wiki/LINPACK_benchmarks): High-Performance Linpack.
- [**LightGBM**](https://lightgbm.readthedocs.io/): Gradient-boosted tree library.
- [**LLM**](https://en.wikipedia.org/wiki/Large_language_model): Large language model.
- [**MISO**](https://www.misoenergy.org/): Midcontinent ISO.
- [**PCC**](https://en.wikipedia.org/wiki/Point_of_common_coupling): Point of common coupling.
- [**PJM**](https://www.pjm.com/): Mid-Atlantic/Midwest grid operator.
- [**PMU**](https://en.wikipedia.org/wiki/Phasor_measurement_unit): Phasor measurement unit.
- [**PNNL**](https://www.pnnl.gov/): Pacific Northwest National Laboratory.
- [**Power Electronics**](https://www.power-electronics.com/): Spanish power-conversion maker (AIPCS).
- [**Ride-through**](https://en.wikipedia.org/wiki/Fault_ride_through): Staying connected through grid disturbances.
- [**SLO**](https://en.wikipedia.org/wiki/Service-level_objective): Service-level objective.
- [**SST**](https://en.wikipedia.org/wiki/Solid-state_transformer): Solid-state transformer.
- [**UPS**](https://en.wikipedia.org/wiki/Uninterruptible_power_supply): Uninterruptible power supply.
- [**Wood Mackenzie**](https://www.woodmac.com/): Energy research firm.

---

_How useful was today's brief? Reply in Grok Bot chat with an overall rating (1–5) and, if you like, per-item ratings (1–9)._
