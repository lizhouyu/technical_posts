---
title: "OpenAI Grid Protectors; Query Routing as Inference Flex"
date: 2026-11-05 08:30:00 +0800
categories: [Daily Brief, Power]
tags: [demand-response, ramp-smoothing, inference, grid, 800vdc, industry, academia, adjacent]
description: "OpenAI turns its 1 GW Georgia curtailment deal into a national program; BESS and gas go behind the meter to absorb AI swings; query routing gives interactive inference 16% power flex in ~10 s; BO-tuned battery+supercap smoothing kills a 0.5 Hz forcing mode."
media_subpath: /assets/img/briefs/2026-11-05/
image:
  path: fig-response-ladder.png
  alt: Response-time ladder for storage, query routing and grid-program deadlines
math: true
mermaid: true
---

## At a glance

[OpenAI](https://en.wikipedia.org/wiki/OpenAI "US AI lab behind ChatGPT; it is building gigawatt-scale compute campuses with partners such as Oracle and utilities such as Georgia Power.") launched a national [Grid Protectors Program](https://openai.com/index/grid-protectors-program "OpenAI program announced Nov 2 2026: a non-binding commitment to negotiate, campus by campus, how much demand it can cut, how fast and for how long when the grid is stressed. The Effingham County, Georgia campus is the pilot.") built on a 1,000 MW [demand-response](https://en.wikipedia.org/wiki/Demand_response "Demand response, DR: a large customer cuts or shifts consumption when the grid is stressed, in exchange for payment or faster interconnection, as an alternative to building new supply.") deal with [Georgia Power](https://en.wikipedia.org/wiki/Georgia_Power "The investor-owned electric utility serving most of Georgia, USA; a subsidiary of Southern Company."). Trade press says [behind-the-meter](https://en.wikipedia.org/wiki/Distributed_generation "Behind-the-meter, BTM: generation or storage on the customer side of the utility meter that serves the load directly rather than through the grid.") gas plus [BESS](https://en.wikipedia.org/wiki/Battery_energy_storage_system "Battery energy storage system: battery cells plus inverters, telemetry and controls that absorb or inject power in real time; used at AI sites for ramp smoothing, ride-through and backup transfer.") is becoming the default way to absorb AI power swings. [TrendForce](https://www.trendforce.com/ "Taiwan-based market-intelligence firm that publishes a monthly AI data-center capacity tracker.") counts three-quarters of October's new tracked capacity on self-powered campuses. [Vertiv](https://www.vertiv.com/en-us/ "US maker of data-center power equipment such as UPS, switchgear and busway, and of thermal-management systems.") locked in [SiC](https://en.wikipedia.org/wiki/Silicon_carbide "Silicon carbide: a wide-bandgap semiconductor used in high-voltage, high-efficiency power converters such as rectifiers and solid-state transformers.") supply for its [800 VDC](https://www.nvidia.com/en-us/data-center/technologies/800-vdc-architecture/ "Distributing power to AI racks at 800 V direct current instead of 54 V DC in-rack or 415/480 V AC, which cuts current and copper for 100 kW to 1 MW racks.") line. On the academic side, a CMU and Bosch paper shows that **query routing** gives interactive inference about 16% power flexibility within about 10 s. A University of Michigan-Dearborn paper tunes battery-plus-[supercapacitor](https://en.wikipedia.org/wiki/Supercapacitor "A capacitor with very high capacitance that can absorb or deliver large power bursts for seconds, with far more cycle life than a battery but little energy.") smoothing offline so it can run with no online optimizer. The common thread is that flexibility is being contracted in **MW and minutes**, while the engineering is now about proving **seconds and Hz**.

> Mix for this weekday digest: 4 industry / 2 academia / 1 adjacent (~57/29/14%).
{: .prompt-tip }

![Response-time ladder](fig-response-ladder.png){: w="1380" h="660" }
_Figure 1. Response times on a log scale. The storage values are converter time constants from the simulation in arXiv:2611.03436. The query-routing t90 comes from the 10,000-GPU simulation in arXiv:2611.05148. The grid-program deadlines are as the authors of 2611.05148 summarize them in their Table B.4. All of these are simulated or quoted values, not field measurements._

## Key developments

### 1. OpenAI launches Grid Protectors; Effingham GA is the 1 GW pilot · Nov 2 2026 · industry / grid

OpenAI says its future campuses will negotiate how much load they can cut, how quickly, and for how long. Where local needs and equipment allow, it says it will also "use batteries and power controls to smooth changes in demand." The pilot is the planned Effingham County campus, which Georgia Power expects to need about **3,200 MW**. A 25-year agreement lets the utility curtail **up to 1,000 MW** (about 31%). [TechTarget](https://www.techtarget.com/news/openai-takes-data-center-power-flexibility-pledge-national/873751/ "TechTarget: US B2B technology publisher; its Nov 4 2026 article analyses the Grid Protectors announcement.") notes that Georgia Power would not disclose the call conditions or how the 1,000 MW will be measured and verified. The Georgia terms date from July and were approved in August. What is new is that OpenAI has made the structure a named national program. Coverage describes it as non-binding.

**Caveats and implications.** These are contract terms, not demonstrated curtailment. An analyst quoted by TechTarget says the cut should be measured at the [POI](https://en.wikipedia.org/wiki/Point_of_common_coupling "Point of interconnection: where the site connects to the utility grid and where contract limits such as peak MW and ramp MW/min are measured.") and should include the **rebound** when deferred work resumes. That is the same ramp-down/ramp-up problem that oversubscription controllers face, only at gigawatt scale. Inference is harder to interrupt than training, so a cap of roughly 31% of campus load implies either a large share of deferrable training or batch work, or on-site storage and generation. For anyone designing capping controllers, the requirement is now a **sustained** cap with bounded recovery ramp, on top of a peak cap.

- [OpenAI: Introducing the Grid Protectors Program](https://openai.com/index/grid-protectors-program)
- [TechTarget: OpenAI takes data center power-flexibility pledge national](https://www.techtarget.com/news/openai-takes-data-center-power-flexibility-pledge-national/873751/)

### 2. BTM gas and BESS become the AI swing absorber · Nov 4 2026 · industry / ramp smoothing

[Power Engineering](https://www.power-eng.com/ "Power Engineering: a trade publication covering power generation and grid technology.") reports [Omdia](https://omdia.tech.informa.com/ "Omdia: technology research and analyst firm, part of Informa TechTarget.")'s projection that data centers could deploy **35 GW of BTM power by 2030**, and that BESS spending could exceed **$50 B/yr by 2030**, up from about $10 B in 2026. Both are analyst forecasts. Oracle's [OCI](https://en.wikipedia.org/wiki/Oracle_Cloud "Oracle Cloud Infrastructure, Oracle's public cloud.") AI infrastructure VP is quoted saying that grids and power plants "can't cope with the massive power swings produced from AI data centers that can happen several times a second" and that BESS used as a buffer "is emerging as a new requirement." Frontier Infrastructure's order of 16 Baker Hughes turbines comes with BESS and [synchronous condensers](https://en.wikipedia.org/wiki/Synchronous_condenser "A spinning synchronous machine run without a prime mover to supply inertia, short-circuit strength and reactive power to the grid.") with generation planned to manage rapid demand changes. The Monarch campus in West Virginia (100+ Caterpillar 1.5 MW gas gensets) relies on BESS for rapid load swings.

**Implication.** Ramp smoothing is moving out of the rack and the GPU (firmware floors, sidecar capacitors) into the plant design itself. On an islanded or weakly connected gas campus there is no grid to hide behind. Engine and turbine governors set the allowable step and ramp, so the BESS or [UPS](https://en.wikipedia.org/wiki/Uninterruptible_power_supply "Uninterruptible power supply: batteries plus converters that keep IT running through outages; some now offer power-smoothing modes.") becomes the primary smoothing layer, not a backup one. This is a trade-press roundup, and the vendor quotes are claims.

- [Power Engineering: Gas turbines and batteries are cashing in as AI data centers can't wait for the grid](https://www.power-eng.com/onsite-power/gas-turbines-batteries-ai-data-centers-grid/)

### 3. TrendForce: new capacity follows self-supplied power; Port Washington halved for 2027 · Nov 4 2026 · industry / grid

TrendForce's November tracker counts **+4,170 MW** of tracked capacity changes in October. Of that, **3,111 MW (~75%)** sits on campuses built next to their own power supply, for example Google Tembo with Black Hills Energy gas and AWS Homer City around a 4.5 GW gas plant. For Vantage's 1.3 GW Lighthouse campus for Oracle and OpenAI in Port Washington, Wisconsin, TrendForce cut its 2027 forecast from **650 MW to 310 MW**. The buildings are enclosed, but the transmission application (over $2 B, five substations) is behind.

**Implication.** The binding constraint keeps moving from construction to the power interface. Self-supplied sites put fast transient and ramp management on the operator (see item 2). Delayed grid ties increase the value of oversubscribing whatever capacity is already energized, which is POLCA-style headroom harvesting at the campus level. These are tracker estimates, not operator disclosures.

- [TrendForce: Where Are AI Data Centers Going? Power Is the Key](https://www.trendforce.com/insights/data-center-tracker-002)

![Power-first build-out numbers](fig-power-first-buildout.png){: w="1500" h="540" }
_Figure 2. Numbers as published. Left and middle: TrendForce tracker, Nov 4 2026. Right: OpenAI / Georgia Power Effingham terms. The right panel shows contracted maximum curtailment, not measured performance._

### 4. Vertiv–Infineon three-year Si/SiC supply deal covering 800 VDC systems · Nov 4 2026 · industry / rack-facility power

Vertiv announced a three-year strategic agreement with [Infineon](https://en.wikipedia.org/wiki/Infineon_Technologies "German semiconductor maker and a leading supplier of power semiconductors such as IGBT, SiC and GaN devices.") for silicon, [IGBT](https://en.wikipedia.org/wiki/Insulated-gate_bipolar_transistor "Insulated-gate bipolar transistor: a high-power switching device widely used in UPS, rectifiers and inverters.") and SiC power semiconductors across its global power portfolio, explicitly including its next-generation 800 VDC power systems. It also commits both companies to align technology and product roadmaps. Volumes and pricing were not disclosed.

**Implication.** This is a small item, but it fits the pattern. 800 VDC rectifiers, solid-state breakers and [SSTs](https://en.wikipedia.org/wiki/Solid-state_transformer "Solid-state transformer: a transformer built from high-frequency power electronics instead of a large 50/60 Hz iron core; in AI data centers it can step medium-voltage AC directly to 800 VDC.") are SiC-heavy, and vendors are now securing supply ahead of 2027 [Kyber](https://developer.nvidia.com/blog/nvidia-800-v-hvdc-architecture-will-power-the-next-generation-of-ai-factories/ "NVIDIA Kyber: the 2027 rack architecture for Rubin Ultra, designed around 800 VDC power delivery.")-class racks. This is a supply and press-release story, not a technical result.

- [Vertiv: Vertiv and Infineon deepen strategic partnership for critical power infrastructure](https://www.vertiv.com/en-us/about/news-and-events/corporate-news/2026/vertiv-and-infineon-deepen-strategic-partnership-for-critical-power-infrastructure/)

### 5. Query routing as a power-flex knob for interactive inference · arXiv Nov 3 2026 · academia / inference capping

Patel, Chen, Fernandez, Qu and Joshi ([CMU](https://en.wikipedia.org/wiki/Carnegie_Mellon_University "Carnegie Mellon University, Pittsburgh, USA."), Bosch Center for AI, Cornell) treat the choice of which model serves a query as a power lever. When queries are equally well served by a small or a large model, shifting the routing fraction toward small-model instances lowers power **without dropping or deferring requests**. The model is analytical: token time is linear in concurrency, $\tau(b)=t_0+t_1 b$, and [Little's law](https://en.wikipedia.org/wiki/Little%27s_law "Queueing identity: average number in system equals arrival rate times average time in system.") connects arrival rate to concurrency and then to board power. It predicts achievable flexibility with **2.8% mean error** across four GPU types and 1B–70B models on [vLLM](https://github.com/vllm-project/vllm "vLLM: open-source high-throughput LLM inference and serving engine.").

The authors simulate 10,000 [H100](https://www.nvidia.com/en-us/data-center/h100/ "NVIDIA H100: Hopper-generation data-center GPU, rated up to 700 W in SXM form.") GPUs replaying the week-long Azure trace from [DynamoLLM](https://arxiv.org/abs/2408.00741 "DynamoLLM, Stojkovic et al., HPCA 2025: energy-optimized LLM inference clusters that reconfigure instances, parallelism and GPU frequency; a seed paper in this digest.") (GPUs split 3:1 between Llama-3.1-70B and Mistral-24B instances, with an assumed 300 W per GPU of non-GPU overhead and [PUE](https://en.wikipedia.org/wiki/Power_usage_effectiveness "Power usage effectiveness: total facility power divided by IT power; 1.0 would mean zero overhead.") of 1.2). The result is mean flexibility of up to **1.19 MW (16%)** when all queries are flexible and 0.6 MW at 50%, with **t90 ≈ 10 s** during a 4-hour curtailment. In the appendix, a [PID](https://en.wikipedia.org/wiki/Proportional%E2%80%93integral%E2%80%93derivative_controller "Proportional-integral-derivative controller: a classic feedback controller that drives an error signal toward zero.") loop cuts mean-power error from 34 W to 14 W, but it adds power jitter and raises median t90 from 6.5 s to 12 s.

**Caveats and implications.** Everything above 4-GPU scale is simulation, and the method assumes a router has already labelled queries as model-indifferent. Quality loss is assumed away, not measured. Flexibility also shrinks at high load, which is exactly when the grid asks for it. Still, routing is a third lever next to [POLCA](https://arxiv.org/abs/2308.12908 "POLCA: Power Oversubscription in LLM Cloud Providers, Patel et al., Microsoft, ASPLOS 2024; characterizes LLM power headroom and an oversubscription and capping framework.")-style frequency caps and DynamoLLM reconfiguration, and it composes with both. The paper itself says it cannot meet sub-second programs such as ERCOT FFR without a battery or UPS in front (Figure 1).

- [arXiv:2611.05148: Creating Power Flexibility in Datacenters via Query Routing](https://arxiv.org/abs/2611.05148)

### 6. Bayesian-optimized battery+supercap smoothing that targets the grid mode · arXiv Nov 2 2026 · academia / ramp smoothing

Mohammadi, Hoang, Wada, Bui and Su (University of Michigan-Dearborn) follow up on last month's grid-mode-aware [MPC](https://en.wikipedia.org/wiki/Model_predictive_control "Model predictive control: repeatedly solves a short-horizon optimization using a system model and applies the first move.") ([arXiv:2609.04398](https://arxiv.org/abs/2609.04398 "Chen, Grid-Mode-Aware Model Predictive Control of Hybrid Energy Storage Systems for AI Data Center Power Smoothing, arXiv Sep 2026.")). They replace online optimization with a **fixed five-parameter controller**: a low-pass split between BESS and supercap, a band-pass modal-compensation gain, and state-of-charge restoration. The parameters are tuned **offline** with [Bayesian optimization](https://en.wikipedia.org/wiki/Bayesian_optimization "Black-box optimization that fits a probabilistic surrogate such as a Gaussian process and picks the next trial point with an acquisition function.") over 10 stochastic workload profiles and tested on 20 unseen ones. In simulation, a 75–160 MW raw load is held mostly within a **120–130 MW** envelope under a 1 MW/s ramp limit. The **20 MW, 0.5 Hz** forcing component drops below 1 MW, Without storage, the grid frequency oscillates between about 59.85 and 60.15 Hz. With the full controller it stays close to 60 Hz apart from brief burst transients. The storage is a 40 MW BESS with a 4–36 MWh operating range plus a 20 MW supercap.

**Caveats and implications.** The load is synthetic (an [OU](https://en.wikipedia.org/wiki/Ornstein%E2%80%93Uhlenbeck_process "Ornstein-Uhlenbeck process: a mean-reverting random process often used to model fluctuating load.") process plus Poisson bursts plus an injected sinusoid), and the grid is an aggregate swing model with a single 0.5 Hz mode. The ablation is more honest than the title: generic low-pass smoothing already removes most of the resonance, and the explicit modal term mostly cleans up the residual. The practical takeaway is that a **forecast-free, explicit controller** is easy to certify and run on a UPS or BESS controller, which matters more for deployment than MPC optimality.

- [arXiv:2611.03436: Grid-Mode-Aware AI Data Center Power Smoothing via Bayesian-Optimized HESS](https://arxiv.org/abs/2611.03436)

### 7. Lumen + Emerald AI: route data toward available power · Nov 2 2026 · adjacent / sustainable AI

[Lumen](https://en.wikipedia.org/wiki/Lumen_Technologies "Lumen Technologies: US network and fiber operator, formerly CenturyLink.") is pairing its programmable network with [Emerald AI](https://www.emeraldai.co/ "Emerald AI: startup whose Conductor software orchestrates AI workloads so data centers can flex power on grid request.")'s Conductor so that customers whose workloads are "power aware" can have their data steered toward sites with available power, not just available GPUs. Lumen says the savings for customers are unclear, and the 100 GW figure that Emerald AI cites for freeing grid capacity is a company claim.

**Implication.** Spatial shifting is the slow-timescale counterpart to item 5. Moving work between sites (minutes to hours) and rerouting between models in one site (seconds) can be stacked. The network becomes part of the demand-response chain, which raises latency and data-residency questions that power papers usually leave out.

- [Fierce Network: Lumen wants to use the network to help AI workloads chase power](https://www.fierce-network.com/broadband/lumen-wants-use-network-help-ai-workloads-chase-power)

## Spotlight: how much flex does routing really have?

From arXiv:2611.05148, with flexible-query share $\sigma_F$, routing fraction $f$ (flexible queries sent to the small pool), and pool capacities $n_L C_L$, $n_S C_S$, capacity limits the feasible routing to

$$
f_{\mathrm{lo}}=\max\!\Big(0,\tfrac{\Lambda(\sigma_L+\sigma_F)-n_L C_L}{\Lambda\sigma_F}\Big)\;\le f\le\;
f_{\mathrm{hi}}=\min\!\Big(1,\tfrac{n_S C_S-\Lambda\sigma_S}{\Lambda\sigma_F}\Big),
\qquad
B(\Lambda)=\max_{f}P_{\mathrm{tot}}-\min_{f}P_{\mathrm{tot}}
$$

As arrival rate $\Lambda$ rises, the small pool's headroom $n_S C_S-\Lambda\sigma_S$ shrinks, so the band $B(\Lambda)$ is largest at **intermediate** load and narrowest at peak. That is the opposite of what a grid operator wants in a heat wave. In the paper's 4-instance example, raising $\Lambda$ from 66 to 119 req/s shrinks the feasible $f$ range from [0.01, 1] to [0.45, 0.58]. For an oversubscribed inference hall, this means routing flex should be counted as **conditional** capacity and backed by storage or a frequency cap at peak.

## Bottom line

Contracted AI-campus flexibility has reached the gigawatt scale (OpenAI/Georgia), and new capacity increasingly sits behind its own meter, where BESS and gas governors decide the ramp. The research is filling in the fast layers. Routing gives inference a seconds-scale knob that needs no deferral, and offline-tuned battery-plus-supercap control targets the specific grid mode at sub-second timescales. Nothing today is a field measurement. The open item is verified, POI-metered curtailment with a bounded rebound ramp.

## Glossary

_Hover any linked term above for a quick definition; click it for the source._

- [**800 VDC**](https://www.nvidia.com/en-us/data-center/technologies/800-vdc-architecture/): Distributing power to AI racks at 800 V direct current instead of 54 V DC in-rack or 415/480 V AC.
- [**Bayesian optimization**](https://en.wikipedia.org/wiki/Bayesian_optimization): Black-box optimization using a probabilistic surrogate and an acquisition function.
- [**BESS**](https://en.wikipedia.org/wiki/Battery_energy_storage_system): Battery energy storage system used for ramp smoothing, ride-through and backup.
- [**Behind-the-meter (BTM)**](https://en.wikipedia.org/wiki/Distributed_generation): Generation or storage on the customer side of the utility meter.
- [**Demand response**](https://en.wikipedia.org/wiki/Demand_response): A large load cuts or shifts consumption on grid request.
- [**DynamoLLM**](https://arxiv.org/abs/2408.00741): HPCA 2025 energy-optimized LLM inference cluster reconfiguration (seed paper).
- [**Emerald AI**](https://www.emeraldai.co/): Startup whose Conductor software flexes data-center power on grid request.
- [**Georgia Power**](https://en.wikipedia.org/wiki/Georgia_Power): Southern Company utility serving most of Georgia.
- [**Grid Protectors Program**](https://openai.com/index/grid-protectors-program): OpenAI's non-binding national campus-flexibility program (Nov 2 2026).
- [**H100**](https://www.nvidia.com/en-us/data-center/h100/): NVIDIA Hopper data-center GPU.
- [**IGBT**](https://en.wikipedia.org/wiki/Insulated-gate_bipolar_transistor): High-power switching transistor used in UPS and inverters.
- [**Infineon**](https://en.wikipedia.org/wiki/Infineon_Technologies): German power-semiconductor maker.
- [**Kyber**](https://developer.nvidia.com/blog/nvidia-800-v-hvdc-architecture-will-power-the-next-generation-of-ai-factories/): NVIDIA's 2027 800 VDC rack architecture for Rubin Ultra.
- [**Little's law**](https://en.wikipedia.org/wiki/Little%27s_law): Items in system = arrival rate × time in system.
- [**Lumen**](https://en.wikipedia.org/wiki/Lumen_Technologies): US network operator, formerly CenturyLink.
- [**MPC**](https://en.wikipedia.org/wiki/Model_predictive_control): Model predictive control, receding-horizon optimization.
- [**OCI**](https://en.wikipedia.org/wiki/Oracle_Cloud): Oracle Cloud Infrastructure.
- [**Omdia**](https://omdia.tech.informa.com/): Technology analyst firm.
- [**OpenAI**](https://en.wikipedia.org/wiki/OpenAI): AI lab building gigawatt-scale compute campuses.
- [**OU process**](https://en.wikipedia.org/wiki/Ornstein%E2%80%93Uhlenbeck_process): Mean-reverting random process used to model fluctuating load.
- [**PID**](https://en.wikipedia.org/wiki/Proportional%E2%80%93integral%E2%80%93derivative_controller): Proportional-integral-derivative feedback controller.
- [**POI**](https://en.wikipedia.org/wiki/Point_of_common_coupling): Point of interconnection where contract limits are measured.
- [**POLCA**](https://arxiv.org/abs/2308.12908): ASPLOS 2024 LLM power oversubscription framework (seed paper).
- [**Power Engineering**](https://www.power-eng.com/): Power-generation trade publication.
- [**PUE**](https://en.wikipedia.org/wiki/Power_usage_effectiveness): Facility power ÷ IT power.
- [**SiC**](https://en.wikipedia.org/wiki/Silicon_carbide): Wide-bandgap semiconductor for high-voltage converters.
- [**SST**](https://en.wikipedia.org/wiki/Solid-state_transformer): Power-electronic transformer that can output 800 VDC directly.
- [**Supercapacitor**](https://en.wikipedia.org/wiki/Supercapacitor): High-power, low-energy storage for second-scale bursts.
- [**Synchronous condenser**](https://en.wikipedia.org/wiki/Synchronous_condenser): Spinning machine that adds inertia and reactive support.
- [**TechTarget**](https://www.techtarget.com/news/openai-takes-data-center-power-flexibility-pledge-national/873751/): B2B tech publisher (item 1 analysis).
- [**TrendForce**](https://www.trendforce.com/): Market-intelligence firm with a monthly data-center tracker.
- [**UPS**](https://en.wikipedia.org/wiki/Uninterruptible_power_supply): Uninterruptible power supply.
- [**Vertiv**](https://www.vertiv.com/en-us/): Data-center power and thermal equipment maker.
- [**vLLM**](https://github.com/vllm-project/vllm): Open-source LLM serving engine.

---

_How useful was today's brief? Reply in Grok Bot chat with an overall rating (1–5) and, optionally, per-item ratings (1–7)._
