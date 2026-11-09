---
title: "Grid access for certainty; Max-Q halls; the 10 MW / 5 s ramp box"
date: 2026-11-09 08:30:00 +0800
categories: [Daily Brief, Power]
tags: [grid, ramp-smoothing, power-capping, max-q, 800vdc, training, dvfs, industry, academia, adjacent]
description: "Grid operators now trade faster interconnection for ramp limits, curtailment and disconnect rights, and ERCOT's draft 10 MW / 5 s variation limit makes ramp smoothing a design requirement. Google and Anthropic buy their own generation. Schneider's RD115 hall fits 56 Max-Q racks where only 42 fit at Max-P. NVIDIA's EE-RL cuts RL post-training GPU energy by up to 16.9%. Also: stochastic transmission planning for data centers that may never be built, and grid-forming storage that damps generator shaft torque."
media_subpath: /assets/img/briefs/2026-11-09/
image:
  path: fig-rd115-states.png
  alt: Schneider RD115 operating states, with 42 racks at Max-P versus 56 at Max-Q in the same hall
math: true
---

## At a glance

A Nov 6 [Utility Dive](https://www.utilitydive.com/ "Utility Dive: trade publication covering US electric utilities, grid operators and large loads.") column lays out the deal now on offer across US grids: interconnect faster in exchange for **certainty**. That means minimum-bill commitments in Ohio, curtailment under [ERCOT](https://www.ercot.com/ "Electric Reliability Council of Texas: grid operator for about 90% of Texas load.") real-time control, and ramp-rate limits plus remote disconnect in [SPP](https://www.spp.org/ "Southwest Power Pool: regional transmission organization covering parts of 14 central US states."). ERCOT's still-unfiled draft limit of **10 MW peak-to-peak in any 5 s** turns ramp smoothing into a sizing constraint. On the supply side, [Google](https://blog.google/innovation-and-ai/infrastructure-and-cloud/global-network/wyoming-data-center/ "Google: announced a $17 B Cheyenne, Wyoming data-center campus on Nov 5 2026.") announced a $17 B Wyoming campus built around **702 MW** of [Bloom Energy](https://www.bloomenergy.com/ "Bloom Energy: maker of solid-oxide fuel cells that generate electricity from natural gas or hydrogen without combustion.") fuel cells, and [Anthropic](https://www.anthropic.com/ "Anthropic: AI company that develops the Claude family of models.") reportedly locked in **1.7 GW** of gas generators. Inside the hall, [Schneider Electric](https://www.se.com/ww/en/about-us/newsroom/news/press-releases/schneider-electric-unveils-new-prefabricated-reference-design-engineered-for-modular-ai-factories-6ad897b234aa2622b80876bf/ "Schneider Electric: French electrical-equipment maker of UPS, switchgear, cooling and prefabricated data-center modules.")'s RD115 reference design is effectively a power-capping oversubscription plan. On the research side, [NVIDIA](https://www.nvidia.com/ "NVIDIA: US GPU and AI-systems company.")'s EE-RL saves RL post-training energy with per-phase [DVFS](https://en.wikipedia.org/wiki/Dynamic_frequency_scaling "Dynamic voltage and frequency scaling: lowering a chip's clock (and voltage) to cut power when full speed is not needed."), a Harvard paper plans transmission for data centers that may never be built, and [PNNL](https://www.pnnl.gov/ "Pacific Northwest National Laboratory: US Department of Energy national lab with a large grid-research program.") shows grid-forming storage damping generator shaft torque.

> Mix for this weekday digest: 4 industry / 3 academia / 1 adjacent (~50/38/12%). No new ramp-smoothing arXiv paper appeared in the Nov 6 listings, so the academic ramp slot is a peer-reviewed IEEE Access paper not covered here before (indexed by PNNL Oct 16).
{: .prompt-tip }

## Key developments

### 1. Grid access in exchange for certainty, and ERCOT's draft 10 MW / 5 s variation limit · Nov 6 2026 · industry / grid & ramp smoothing

In a Nov 6 Utility Dive column, Seyed Madaeni, CEO of [Verse](https://www.verse.inc/ "Verse: energy-software company that optimizes battery dispatch for data centers."), argues that a "third path" to interconnection is forming: data centers get faster or more certain service if they make their demand "more predictable, controllable and financially secure." His examples:

- **Ohio:** a settlement on the [AEP](https://www.aep.com/ "American Electric Power: US utility holding company with operating companies in 11 states, including AEP Ohio.") Ohio data-center tariff makes large customers pay for up to **85%** of subscribed capacity even when they use less, in exchange for lifting a connection moratorium.
- **ERCOT:** a facility must meet [ride-through](https://www.ercot.com/mktrules/issues/NOGRR282 "Ride-through: a load must stay connected through specified voltage and frequency disturbances instead of tripping offline. ERCOT NOGRR 282 sets this for large computational loads.") requirements. In [Batch Zero](https://www.ercot.com/files/docs/2026/09/11/14-Batch-Zero-Update.pdf "ERCOT Batch Zero: the first cluster-study batch for large-load interconnection in Texas under PGRR 145."), developers can choose dispatchable curtailment under ERCOT's real-time control in exchange for earlier energization.
- **SPP:** the High Impact Large Load framework completes interconnection studies within **90 days** for developers that accept real-time forecast reporting, **ramp-rate limits** and **remote disconnect**.
- **PJM:** [FERC](https://www.ferc.gov/ "Federal Energy Regulatory Commission: US regulator of interstate transmission and wholesale power markets.") rejected most of [PJM](https://www.pjm.com/ "PJM Interconnection: regional grid operator for 13 eastern US states and DC.")'s [IRAS](https://www.pjm.com/pjmfiles/directory/etariff/FercOrders/9207/20261009-er26-3515-000.pdf "Interim Resource Adequacy Service: PJM's proposal that new large loads without matching new capacity accept emergency load-reduction requests. FERC accepted only the Large Load definition (50 MW) and registry.") curtailment framework in October, but it left states free to decide who gets curtailed under stress.

This is an opinion piece by a battery-dispatch vendor. Read it as a map of the rules, not a neutral assessment.

The column says nothing about how tight the ramp box could get. ERCOT's [Large Load Working Group](https://www.ercot.com/files/docs/2026/02/19/ERCOT-LEL-SSO-Power-Variation-Consideration.pdf "ERCOT Feb 2026 LLWG deck proposing a large-load power variation requirement.") materials do. They propose that a [large computational load](https://www.ercot.com/files/docs/2026/04/24/ERCOT-Large-Computational-Load-LCL-Power-Variation-Limit-and-Monitoring-Requirement-Need-and-Discussion_fin.pdf "ERCOT April 2026 deck: LCL Power Variation Limit and Monitoring Requirement.") vary its active power by no more than **10 MW peak-to-peak within any 5-second period**. The goal is to stop persistent, repetitive swings from exciting the [torsional modes](https://en.wikipedia.org/wiki/Subsynchronous_resonance "Sub-synchronous oscillation / torsional interaction: power oscillations below the grid's 60 Hz that can resonate with the shafts of nearby steam and gas turbine-generators and fatigue them.") of nearby synchronous generators. The April deck also warns that correlated swings across several sites could add up, and that monitoring may need [PMU](https://en.wikipedia.org/wiki/Phasor_measurement_unit "Phasor measurement unit: a high-rate, GPS-time-stamped grid sensor.") rates above **30 samples/s**. As of Nov 3, engineering firm [GridAxon](https://gridaxon.io/insights/sso-ercot-10-mw-5-second-rule.html "GridAxon: grid-engineering consultancy; its Nov 3 2026 note summarizes the ERCOT rule's status.") says it could not find a numbered revision request. It reports that the draft measures content from **0.1 to 55 Hz** and that ERCOT has said infrequent single steps above 10 MW would not violate the limit. **Treat it as a draft.**

**Implication.** For a 300 MW campus, 10 MW is about **3%** of load. Capping the training cycle alone will not get a synchronous job's compute-to-communication swing inside that box. You need storage or UPS-side smoothing, staggered phases, or [GB300-style](https://developer.nvidia.com/blog/how-new-gb300-nvl72-features-provide-steady-power-for-ai/ "NVIDIA GB300 NVL72 power smoothing: energy storage in the power shelves, a power floor, and a 'power burner' on ramp-down.") rack features, plus PMU-grade evidence at the point of interconnection. The interconnection queue is turning ramp-smoothing hardware into a ticket to faster energization.

![Illustrative 10 MW / 5 s box](fig-ercot-10mw-5s.png){: w="1400" h="602" }
_Figure 1. **Illustrative schematic, not data.** It shows a made-up 30 MW, 0.5 Hz training swing on a 300 MW campus and a storage-smoothed grid-side draw against ERCOT's draft 10 MW peak-to-peak / 5 s window. Only the 10 MW / 5 s / 0.1–55 Hz parameters come from ERCOT and GridAxon._

- [Utility Dive: Data centers don't need special treatment to get power faster (Nov 6 2026)](https://www.utilitydive.com/news/data-centers-grid-flexibility-tariffs-ercot-spp-pjm/833678/)
- [ERCOT LLWG: LCL Power Variation Limit and Monitoring Requirement (Apr 2026, PDF)](https://www.ercot.com/files/docs/2026/04/24/ERCOT-Large-Computational-Load-LCL-Power-Variation-Limit-and-Monitoring-Requirement-Need-and-Discussion_fin.pdf)
- [GridAxon: ERCOT's 10 MW / 5-second rule (Nov 3 2026)](https://gridaxon.io/insights/sso-ercot-10-mw-5-second-rule.html)

### 2. Hyperscalers and labs buy their own generation: Google's 702 MW fuel cells and Anthropic's 1.7 GW of gensets · Nov 5 and Nov 8 2026 · industry / grid & BTM

On Nov 5, Google announced its first Wyoming data center, a **$17 B** investment in Laramie County, with Tallgrass Energy, Black Hills Energy, AEP and Related Digital. Power comes from three sources:

- A **702 MW** fuel-cell plant with [carbon capture and storage](https://en.wikipedia.org/wiki/Carbon_capture_and_storage "CCS: capturing CO2 from a power plant and injecting it into geologic storage."). AEP's release says it will invest about **$4 B** under a 20-year [PPA](https://en.wikipedia.org/wiki/Power_purchase_agreement "Power purchase agreement: a long-term contract to buy electricity from a specific generator.") with Google, start construction in 2026 and finish by the end of 2028.
- Gas generators run by [Tallgrass](https://tallgrass.com/ "Tallgrass Energy: US midstream company that operates the Eastern Wyoming Sequestration Hub.") and [Black Hills Energy](https://www.blackhillsenergy.com/ "Black Hills Energy: utility serving Wyoming and other Mountain West and Plains states.").
- A FEED study on adding CCS to Tallgrass's combined-cycle turbines.

The site will be **air-cooled**. Google says it "will pay for 100% of the power we use."

On Nov 8, [CNBC](https://www.cnbc.com/2026/11/08/anthropic-generator-deal-ai-data-centers.html "CNBC report summarizing a Financial Times story on Anthropic's generator deal.") relayed a Financial Times report that Anthropic agreed to pay about **$3.4 B** in late September for commitments on **1.7 GW** of heavy-duty gas generators from OnePWR Solutions, a San Antonio supplier. The deal reportedly includes engineering and installation capability. Reuters could not verify it, and neither company commented.

**Caveats.** Google has not stated the campus's compute capacity. Anthropic's deal is unconfirmed reporting.

**Implication.** Self-supplied campuses move ramp and transient responsibility inside the fence. Neither announcement says how fuel cells or gas sets will follow synchronous training swings, or how much battery buffering sits between them and the GPUs. As GridAxon notes, on-site synchronous machines may need their own torsional review even where the grid-level 10 MW rule doesn't apply. This is the setting where rack-level smoothing and power caps carry the most value.

- [Google: Investing in Wyoming's infrastructure, energy and workforce (Nov 5 2026)](https://blog.google/innovation-and-ai/infrastructure-and-cloud/global-network/wyoming-data-center/)
- [AEP: 702 MW of Bloom fuel cells for Google (Oct 14 2026)](https://www.aep.com/news/stories/view/12314/)
- [CNBC: Anthropic secures $3.4 billion generator deal, FT reports (Nov 8 2026)](https://www.cnbc.com/2026/11/08/anthropic-generator-deal-ai-data-centers.html)

### 3. Schneider RD115: an operating-point plan that fits 56 Max-Q racks where 42 fit at Max-P · Oct 21 2026 release, Nov 6 trade coverage · industry / hall-level oversubscription

[The Data Center Engineer](https://thedatacenterengineer.com/news/schneider-electric-rapidscale-modular-ai-data-center-design-targets-nvidia-vera-rubin/ "Trade site covering data-center engineering.") covered Schneider's [RapidScale](https://www.se.com/us/en/download/document/RD115DSR0/ "Schneider RapidScale Modular Data Center Reference Design 115: 10–20 MW, Tier III, ANSI, NVIDIA DSX-ready.") Reference Design 115 on Nov 6. Schneider first announced the design at GTC Berlin on Oct 21, alongside a time study with [Compass Datacenters](https://www.compassdatacenters.com/ "Compass Datacenters: US hyperscale data-center developer.") that cut onsite install time per prefabricated pod from **75.5 h to 15 h**. The data sheet is the interesting part. The hall hosts four 1,008-GPU [Vera Rubin NVL72](https://www.nvidia.com/en-us/data-center/vera-rubin-nvl72/ "NVIDIA Vera Rubin NVL72: rack-scale system with 72 Rubin GPUs, successor to GB300 NVL72.") clusters and is sized around **operating states** instead of nameplate:

- **Max-P:** **227 kW** per rack, the highest-token point. **42** AI racks fit.
- **[Max-Q](https://developer.nvidia.com/blog/optimize-data-center-efficiency-for-ai-and-hpc-workloads-with-power-profiles/ "NVIDIA Max-Q workload power profiles: preset GPU power and clock settings that trade some peak speed for better tokens per watt."):** **~188 kW** per rack, the best tokens per watt. All **56** AI racks fit, for **10,528 kW** of AI load and **11,408 kW** of maximum active IT.
- **Average:** ~**156 kW** per rack across workloads. All 56 racks fit.

Power reaches the IT space through four **3.75 MW** powertrains (3+1 distributed redundant) with **5 min** of [UPS](https://en.wikipedia.org/wiki/Uninterruptible_power_supply "Uninterruptible power supply: battery-backed converter that carries load through grid interruptions; modern units can also absorb short load transients.") runtime. Schneider says the UPS overload capacity covers the racks' electrical design point. Facility peak is **13.25 MW**.

**Implication.** The 33% density gain (56 vs 42 racks) comes from a vendor reference design that assumes operators actually enforce the Max-Q profile. That is POLCA-style oversubscription written into a commercial blueprint. The open questions: what enforces the cap when a tenant flips to Max-P, and how fast? And does UPS overload absorb the transient? These are vendor design values, not measurements.

![RD115 operating states](fig-rd115-states.png){: w="1540" h="588" }
_Figure 2. Racks and power at each RD115 operating state. Numbers come from Schneider's RD115 data sheet._

- [Schneider Electric press release: RapidScale RD115 (Oct 21 2026)](https://www.se.com/ww/en/about-us/newsroom/news/press-releases/schneider-electric-unveils-new-prefabricated-reference-design-engineered-for-modular-ai-factories-6ad897b234aa2622b80876bf/)
- [Schneider RD115 data sheet (RD115DSR0)](https://www.se.com/us/en/download/document/RD115DSR0/)
- [The Data Center Engineer: RapidScale targets NVIDIA Vera Rubin (Nov 6 2026)](https://thedatacenterengineer.com/news/schneider-electric-rapidscale-modular-ai-data-center-design-targets-nvidia-vera-rubin/)

### 4. Infineon and SOLUM: a 26 kW-class 800 VDC BBU converter targeting 2027 · Nov 5 2026 · industry / rack & PoL

[Infineon](https://www.infineon.com/ "Infineon Technologies: German power-semiconductor maker (Si, SiC, GaN).") and Korean power-module maker [SOLUM](https://www.solum-group.com/ "SOLUM: Korean electronics maker of server power supplies and power modules.") signed an MoU covering [intermediate bus converters](https://www.infineon.com/technology-news/2026/inftn202611-027 "IBC: the stage that steps the rack bus (e.g. 800 V or 54 V) down to ~12/6 V for point-of-load regulators next to the GPU."), BBUs and PSUs for HVDC AI racks. At the signing, SOLUM showed a **26 kW-class [BBU](https://www.solum-group.com/solum/press-release-detail.infineon-mou "Battery backup unit: rack-level battery plus DC/DC converter that carries servers through momentary power interruptions and can also buffer load steps.") DC/DC converter for [800 VDC](https://www.nvidia.com/en-us/data-center/technologies/800-vdc-architecture/ "Distributing power to AI racks at 800 V direct current instead of 54 V DC in-rack or 415/480 V AC.") racks**. It uses CoolSiC [SiC](https://en.wikipedia.org/wiki/Silicon_carbide "Silicon carbide: wide-bandgap semiconductor for high-voltage, high-efficiency power switches.") MOSFETs, targets **>98.5%** peak efficiency, and is aimed at **2027** mass production. SOLUM also showed an [ORv3](https://www.opencompute.org/wiki/Open_Rack "OCP Open Rack v3: Open Compute rack standard with 48/54 V busbar and power shelves.")-compatible **33 kW** power shelf.

**Caveats.** This is an MoU, not a product launch, and the efficiency is a target.

**Implication.** Rack BBUs are among the storage layers closest to the GPU. They sit where Envision-style SST + BESS stacks and GB300 power-shelf storage also compete. An 800 VDC BBU shipping in 2027 lines up with NVIDIA Kyber-era racks. Whether it can also serve as a **ramp-smoothing** buffer, not just ride-through, depends on cycling ratings that aren't disclosed yet.

- [Infineon: Infineon and SOLUM strengthen collaboration on HVDC (Nov 5 2026)](https://www.infineon.com/technology-news/2026/inftn202611-027)
- [SOLUM press release (Nov 5 2026)](https://www.solum-group.com/solum/press-release-detail.infineon-mou)

### 5. EE-RL: online per-phase DVFS cuts RL post-training energy by up to 16.9% · arXiv Nov 3 2026 · academia / training (thin slice)

Sharma, Vegesna and Zhang at NVIDIA observe that RL post-training ([GRPO](https://arxiv.org/abs/2402.03300 "Group Relative Policy Optimization: an RL algorithm that scores several sampled responses per prompt against each other.")) alternates memory-bound generation with compute-bound training. Meanwhile the default GPU governor runs everything near peak clock: **1980 MHz** on [H100](https://www.nvidia.com/en-us/data-center/h100/ "NVIDIA H100: Hopper-generation data-center GPU.") and **2062 MHz** on [GB200](https://www.nvidia.com/en-us/data-center/gb200-nvl72/ "NVIDIA GB200 NVL72: Grace-Blackwell rack-scale system."). EE-RL picks separate generation and training clocks online. It compares each trial against a token-count model of what the governor would have done on the same work, accepts a setting only if it keeps **≥98%** of governor throughput, and drops waiting pools to a **345 MHz** idle clock. Energy is metered over the whole allocation via [NVML](https://developer.nvidia.com/management-library-nvml "NVIDIA Management Library: API for GPU telemetry and control, including energy counters and clock settings.") sampled every 200 ms.

Fixed sweeps show up to **28.2%** headroom on disaggregated H100. Online, including search cost, EE-RL saves **4.1–16.9%** across eight H100 runs with full-run throughput changes between **−1.97% and +1.62%**. After the setting locks, disaggregated Qwen reaches **22.4%**. In asynchronous modes, the controller consistently ends up slowing **training**, not generation.

**Caveats.** Each controller result uses one matched seed. Only GRPO was tested, and the authors flag large run-to-run variation on GB200. Energy is GPU-only, with no CPU, network or cooling.

**Implication.** Phase-aware clocks are becoming standard across inference (DynamoLLM, RAPID) and now RL training. For facility planners, a 15–20% GPU-power reduction during training phases also **shrinks the compute-to-idle swing**, though the paper does not measure ramp behavior.

![EE-RL results](fig-eerl-savings.png){: w="1400" h="616" }
_Figure 3. EE-RL controller results relative to the default governor, from Table 4 of arXiv:2611.05748. H100 runs, full interval including search._

- [arXiv:2611.05748 — Energy-Efficient Reinforcement Learning for Large Language Models](https://arxiv.org/abs/2611.05748)

### 6. Stochastic transmission planning for data centers that may never be built · arXiv Nov 4 2026 · academia / grid interconnection

Dong, Talkington and Xie (Le Xie's group, Harvard) treat each candidate data center as a discrete project that either materializes or doesn't, with an assumed probability. They then compare deterministic "build for all" (Det-All), threshold-screened, stochastic and robust [transmission expansion](https://arxiv.org/abs/2611.05958 "Transmission expansion planning: choosing which lines to build or upgrade so future load and generation can be served reliably at least cost.") plans on investment, [EENS](https://en.wikipedia.org/wiki/Loss_of_load "Expected energy not served: the probability-weighted MWh of load that cannot be served.") and after-the-fact correction cost. The main test system is a synthetic 21-bus Mid-Atlantic network with **seven candidate sites of 3,000 MW each**, **397** probability vectors, and [VOLL](https://en.wikipedia.org/wiki/Value_of_lost_load "Value of lost load: the cost assigned to each MWh of unserved demand in planning models.") of **$10,000/MWh**, cross-checked on a modified IEEE 24-bus system. Stochastic planning gives a better investment-versus-reliability tradeoff than deterministic plans, even when the probabilities are wrong. As VOLL rises, it converges toward the conservative build-for-all plan.

**Caveats.** This is a DC power-flow planning model with no dynamics and no flexibility contracts. The authors call it decision support, not a replacement for reliability criteria.

**Implication.** This gives formal backing to the PJM large-load registry and ERCOT Batch Zero audits: realization probability is now a planning input. The paper does not model it, but a load that commits to curtailment or ramp limits (item 1) arguably reduces the reliability exposure the planner has to hedge against.

- [arXiv:2611.05958 — Transmission Expansion with Large, Discrete Data Center Realization Uncertainty](https://arxiv.org/abs/2611.05958)

### 7. PNNL: grid-forming storage damps AI-training swings and generator shaft torque · IEEE Access 2026 · academia / ramp smoothing

Ross, Lyu, Nwaneto, Mohiuddin and Nassif build an [electromagnetic-transient](https://en.wikipedia.org/wiki/EMTP "EMT simulation: time-domain, sub-cycle modeling of power-electronic and network dynamics.") model of a hyperscale data center with a UPS, co-generator, cooling and a [grid-forming](https://en.wikipedia.org/wiki/Grid-forming_inverter "Grid-forming control: an inverter that sets its own voltage and frequency like a synchronous machine, instead of just following the grid.") energy-storage system, each with explicit converter and control dynamics. They test two stresses: low-voltage faults and fast AI-training fluctuations. A well-tuned GFM ESS reduces frequency overshoot, raises the nadir, shortens settling and improves post-fault recovery. Under fluctuation profiles it **damps active-power oscillations and reduces torsional shaft-torque oscillations** in the generator train.

**Caveats.** The abstract gives no headline numbers, and results depend on tuning. This is simulation, not field data.

**Implication.** This is the physical mechanism behind ERCOT's draft rule (item 1) and the on-site-generation question (item 2). For campuses that run their own co-generators, the evidence favors grid-forming over grid-following storage control as the ramp smoother.

- [PNNL publication page (Oct 16 2026)](https://www.pnnl.gov/publications/using-grid-forming-energy-storage-systems-provide-dynamic-active-power-support)
- [DOI 10.1109/ACCESS.2026.3666746 — IEEE Access 14:29250–29259](https://doi.org/10.1109/ACCESS.2026.3666746)

### 8. The SIMPLE law: a four-parameter model of LLM inference energy · arXiv Nov 2 2026 · adjacent / sustainable AI

Cavagna, Proia, Cesarini, Kiziltan and Bartolini derive closed-form compute and memory-access costs for [MHA and GQA](https://arxiv.org/abs/2305.13245 "Grouped-query attention: several query heads share one key/value head, which shrinks the KV cache compared with multi-head attention.") inference. From these they build **SIMPLE**, a four-parameter energy law that splits prefill from decode, and decode into [KV-cache](https://arxiv.org/abs/2309.06180 "KV cache: stored attention keys/values of past tokens; it grows with sequence length and makes each later token costlier.") cost and next-token compute. Across 13 dense LLMs on H100, it reaches **R² = 0.969** and **11.97% MAPE** without per-model calibration, which the authors say is **3.1–3.5×** lower error than the state of the art. Other findings:

- Prefill energy grows quadratically with hidden dimension.
- Aggressive GQA grouping cuts per-token energy by up to **3×**.
- Intelligence per joule peaks at an intermediate reasoning budget.
- Agentic requests cost **13.0×** more energy than non-agentic ones. [Prefix caching](https://docs.vllm.ai/en/latest/features/automatic_prefix_caching.html "Prefix caching: reusing the KV cache of a shared prompt prefix across requests.") removes ~**93%** of prefill cost but leaves cached agentic requests at **4.8×**.

The paper is submitted to Future Generation Computer Systems, not yet peer-reviewed.

**Implication.** An analytical per-request energy model is the missing input for admission control under a power cap. It lets a capping controller price long-context and agentic requests before admitting them, instead of learning their cost after the fact.

- [arXiv:2611.03330 — The SIMPLE Law for Energy Cost of LLM Inference](https://arxiv.org/abs/2611.03330)

## Spotlight: what "Max-Q provisioning" buys, in one inequality

RD115's operating states reduce to the standard capping-based oversubscription condition. For a hall budget $B$, $N$ racks each capped at $c$, and a fixed overhead $O$ (networking, CDUs):

$$
N\,c + O \;\le\; B
\quad\Rightarrow\quad
N_{\max}(c) = \Big\lfloor \tfrac{B - O}{c} \Big\rfloor .
$$

RD115 also has non-electrical limits: CDU flow per rack is fixed, so cooling helps set the active-rack count. With its numbers (networking ≈ **880 kW**), going from $c = 227$ kW to $c \approx 188$ kW lets the hall hold 56 racks instead of 42 (+33%). Two other constraints have to hold at the same time:

1. **Cap enforcement latency.** The cap has to engage faster than the UPS overload window, or the hall briefly runs at $N \times 227$ kW.
2. **Ramp box.** On an ERCOT-style interconnection, $\max_{t\in[\tau,\tau+5\,\mathrm{s}]} P(t) - \min_{t\in[\tau,\tau+5\,\mathrm{s}]} P(t) \le 10$ MW at the POI, aggregated across halls.

A hall that passes the first inequality can still fail the second if all 56 racks start or stop a synchronous job together.

## Bottom line

This weekend's news was about **terms of access**, not new hardware. Grids now trade speed for curtailment, ramp limits and disconnect rights. ERCOT's draft 10 MW / 5 s box makes smoothing a sizing problem, and the biggest buyers (Google, Anthropic) are buying their own generation, which moves the transient problem inside the fence. At the hall level, Schneider's RD115 quietly makes power capping the basis of density. On the research side, phase-aware DVFS now covers RL training, planners can model data centers that may not get built, and grid-forming storage has peer-reviewed EMT evidence that it protects generator shafts. Still missing: POI-metered field data showing any AI campus inside a 10 MW / 5 s envelope.

## Glossary

_Hover any linked term above for a quick definition; click it for the source._

- [**800 VDC**](https://www.nvidia.com/en-us/data-center/technologies/800-vdc-architecture/): Distributing power to AI racks at 800 V direct current.
- [**AEP**](https://www.aep.com/): American Electric Power, US utility building Google's Cheyenne fuel-cell plant.
- [**Anthropic**](https://www.anthropic.com/): AI company, reportedly buying 1.7 GW of gas generators.
- [**Batch Zero**](https://www.ercot.com/files/docs/2026/09/11/14-Batch-Zero-Update.pdf): ERCOT's first large-load cluster-study batch.
- [**BBU**](https://www.solum-group.com/solum/press-release-detail.infineon-mou): Rack-level battery backup unit.
- [**Bloom Energy**](https://www.bloomenergy.com/): Solid-oxide fuel-cell maker.
- [**CCS**](https://en.wikipedia.org/wiki/Carbon_capture_and_storage): Carbon capture and storage.
- [**Compass Datacenters**](https://www.compassdatacenters.com/): Hyperscale developer, co-author of Schneider White Paper 238.
- [**DVFS**](https://en.wikipedia.org/wiki/Dynamic_frequency_scaling): Dynamic voltage and frequency scaling.
- [**EENS**](https://en.wikipedia.org/wiki/Loss_of_load): Expected energy not served.
- [**EMT**](https://en.wikipedia.org/wiki/EMTP): Electromagnetic-transient simulation.
- [**ERCOT**](https://www.ercot.com/): Texas grid operator.
- [**FERC**](https://www.ferc.gov/): US federal energy regulator.
- [**GB200 / H100**](https://www.nvidia.com/en-us/data-center/gb200-nvl72/): NVIDIA Blackwell and Hopper GPUs.
- [**GQA / MHA**](https://arxiv.org/abs/2305.13245): Grouped-query vs multi-head attention.
- [**Grid-forming (GFM)**](https://en.wikipedia.org/wiki/Grid-forming_inverter): Inverter control that sets voltage and frequency itself.
- [**GRPO**](https://arxiv.org/abs/2402.03300): Group Relative Policy Optimization.
- [**GridAxon**](https://gridaxon.io/insights/sso-ercot-10-mw-5-second-rule.html): Grid-engineering consultancy.
- [**IBC**](https://www.infineon.com/technology-news/2026/inftn202611-027): Intermediate bus converter.
- [**Infineon**](https://www.infineon.com/): German power-semiconductor maker.
- [**IRAS**](https://www.pjm.com/pjmfiles/directory/etariff/FercOrders/9207/20261009-er26-3515-000.pdf): PJM's Interim Resource Adequacy Service (mostly rejected by FERC).
- [**KV cache**](https://arxiv.org/abs/2309.06180): Stored attention keys and values of earlier tokens.
- [**Max-Q / Max-P**](https://developer.nvidia.com/blog/optimize-data-center-efficiency-for-ai-and-hpc-workloads-with-power-profiles/): NVIDIA efficiency-optimal vs performance-optimal power profiles.
- [**NVIDIA**](https://www.nvidia.com/): GPU and AI-systems vendor.
- [**NVML**](https://developer.nvidia.com/management-library-nvml): NVIDIA Management Library.
- [**ORv3**](https://www.opencompute.org/wiki/Open_Rack): OCP Open Rack v3.
- [**PJM**](https://www.pjm.com/): Mid-Atlantic/Midwest grid operator.
- [**PMU**](https://en.wikipedia.org/wiki/Phasor_measurement_unit): Phasor measurement unit.
- [**PNNL**](https://www.pnnl.gov/): Pacific Northwest National Laboratory.
- [**PPA**](https://en.wikipedia.org/wiki/Power_purchase_agreement): Power purchase agreement.
- [**Prefix caching**](https://docs.vllm.ai/en/latest/features/automatic_prefix_caching.html): Reusing a shared prompt's KV cache.
- [**RapidScale RD115**](https://www.se.com/us/en/download/document/RD115DSR0/): Schneider's 10–20 MW modular AI-hall reference design.
- [**Ride-through**](https://www.ercot.com/mktrules/issues/NOGRR282): Staying connected through grid disturbances.
- [**Schneider Electric**](https://www.se.com/ww/en/about-us/newsroom/news/press-releases/schneider-electric-unveils-new-prefabricated-reference-design-engineered-for-modular-ai-factories-6ad897b234aa2622b80876bf/): Electrical and data-center equipment maker.
- [**SiC**](https://en.wikipedia.org/wiki/Silicon_carbide): Silicon carbide power semiconductors.
- [**SOLUM**](https://www.solum-group.com/): Korean server-power module maker.
- [**SPP**](https://www.spp.org/): Southwest Power Pool.
- [**Torsional interaction / SSO**](https://en.wikipedia.org/wiki/Subsynchronous_resonance): Sub-synchronous oscillation that fatigues generator shafts.
- [**UPS**](https://en.wikipedia.org/wiki/Uninterruptible_power_supply): Uninterruptible power supply.
- [**Utility Dive**](https://www.utilitydive.com/): Utility-industry trade press.
- [**Verse**](https://www.verse.inc/): Battery-dispatch software company.
- [**Vera Rubin NVL72**](https://www.nvidia.com/en-us/data-center/vera-rubin-nvl72/): NVIDIA's next rack-scale system.
- [**VOLL**](https://en.wikipedia.org/wiki/Value_of_lost_load): Value of lost load.

---

_How useful was today's brief? Reply in Grok Bot chat with an overall rating (1–5) and, if you like, per-item ratings (1–8)._
