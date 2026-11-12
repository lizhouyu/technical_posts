---
title: "Sub-ms 800 VDC converters; 71% smoother imports; Meta's 160 MW caps"
date: 2026-11-12 08:30:00 +0800
categories: [Daily Brief, Power]
tags: [800vdc, ramp-smoothing, energy-storage, power-capping, inference, training, dvfs, grid, industry, academia, adjacent]
description: "Ampt launches an 80 kW, sub-millisecond 800 VDC battery converter (GA Q3 2027). Vision Group's LiLic sidecar rates 1 MW for at least 60 seconds. BloombergNEF tracks 181 GW of announced on-site gas and projects data-center demand at 2,354 TWh by 2035, 7% of global electricity; Microsoft's Noelle Walsh says the company will pay its own way. Constellation signs a first 20-year, 270 MW Peak+ nuclear contract from 2028. A Monash paper cuts mean minute-to-minute grid-import changes 71.70% with a 1 MW / 1 MWh battery. Meta's HPCA 2027 paper reports end-to-end capping on a 160 MW, 83K-GB200 cluster, with an estimated 10–13% throughput gain versus a 1200 W TDP design. A revised KAIROS paper cuts agentic inference power 27% on one GPU and 46.3% on four. Dartmouth and Purdue quantify a 45.0% lift in admitted large-load capacity when flexible tiers are allowed. Tapestry's HyperQ screens 220 GW of PJM Cycle 1 site-control filings in under a day."
media_subpath: /assets/img/briefs/2026-11-12/
image:
  path: fig-storage-timescales.png
  alt: Vendor-stated time windows for Ampt’s sub-millisecond 800 VDC converter and Vision’s 1 MW / 60 s LiLic sidecar
math: true
---

## At a glance

Two new [800 VDC](https://www.nvidia.com/en-us/data-center/technologies/800-vdc-architecture/ "800 VDC: distributing power to AI racks at 800 V direct current instead of 54 V DC in-rack or low-voltage AC, which cuts current and copper for 100 kW to 1 MW racks.") products landed on Nov 11. [Ampt](https://www.ampt.com/ "Ampt: Fort Collins company whose DC converters have been used in utility-scale solar and storage; it now offers an 800 VDC battery converter for AI data centers.") announced an 80 kW, 2U battery converter that holds regulated 800 VDC from a 1100–1500 VDC battery bus and claims a response to [GPU](https://en.wikipedia.org/wiki/Graphics_processing_unit "Graphics processing unit: the accelerator that dominates AI-rack power.") load changes in less than 1 millisecond, with general availability in Q3 2027. [Vision Group](https://www.vision-batt.com/en/ "Vision Group: battery manufacturer offering lithium and hybrid storage products, including data-center backup and 800 VDC white-space systems.") introduced [LiLic](https://www.vision-batt.com/en/news/show/post-262.html "LiLic: Vision Group’s 800 VDC hybrid power sidecar combining lithium-ion capacitors with LFP batteries for smoothing and short backup."), a white-space sidecar rated at 1 MW for at least 60 seconds. [BloombergNEF](https://about.bnef.com/ "BloombergNEF, BNEF: Bloomberg’s energy-research arm.") projects data-center demand at 2,354 TWh by 2035 (7% of global electricity) and has tracked 181 GW of announced on-site gas, more than 90% of it in the US — a pipeline, not a build forecast. At the same [BNEF](https://about.bnef.com/ "BloombergNEF.") Houston conference, [Microsoft](https://www.microsoft.com/ "Microsoft: the US software and cloud company, including Azure.")’s Noelle Walsh said, “We will pay our own way.” [Constellation](https://www.constellationenergy.com/ "Constellation Energy: US generator and retail supplier with the largest nuclear fleet in the country, much of it in PJM.") signed its first [Peak+](https://www.constellationenergy.com/news/2026/11/constellation-reports-third-quarter-2026-results.html "Peak+: Constellation’s product that pairs energy from the existing nuclear fleet with new capacity, including new generation and demand response.") contract: 270 MW of unit-contingent nuclear energy, capacity and attributes for 20 years, starting in 2028.

On the research side, Zheng et al. (Monash, [arXiv 2611.13694](https://arxiv.org/abs/2611.13694 "Zheng, Jiang, de Nijs, Lam and Wagner: battery-assisted grid-import smoothing for AI data centers with decision-focused learning.")) cut mean minute-to-minute grid-import changes by **71.70%** with a 1 MW / 1 MWh [BESS](https://en.wikipedia.org/wiki/Battery_storage_power_station "Battery energy storage system: a facility- or grid-scale battery used for peak shaving, smoothing and backup.") behind a 10 MW AI facility profile. [Meta](https://www.meta.com/ "Meta Platforms: the company operating Facebook, Instagram and WhatsApp, and a large AI training fleet.")’s [HPCA](https://hpca-conf.org/ "International Symposium on High-Performance Computer Architecture.") 2027 paper reports end-to-end power management for a **160 MW** cluster of **83K [GB200](https://www.nvidia.com/en-us/data-center/gb200-nvl72/ "NVIDIA GB200: Blackwell-generation GPU used in NVIDIA’s NVL72 rack-scale systems.")** GPUs, with an estimated **10–13%** throughput gain versus a 1200 W [TDP](https://en.wikipedia.org/wiki/Thermal_design_power "Thermal design power: the vendor’s hardware design rating, 1200 W for GB200 in this paper.") design. A Nov 10 revision of [KAIROS](https://arxiv.org/abs/2604.16682 "KAIROS: context-aware power manager for agentic LLM serving that jointly sets GPU frequency, concurrency and placement.") reports a 27% average (up to 39.8%) power cut on a single [H100](https://www.nvidia.com/en-us/data-center/h100/ "NVIDIA H100: Hopper-generation data-center GPU; the KAIROS server uses H100 NVL parts with a 400 W TDP.") and 46.3% across four instances. Li, Fang, Chen and Qin ([arXiv 2611.13673](https://arxiv.org/abs/2611.13673 "Priority-aware firm and flexible capacity quantification for large-load interconnection.")) find that multi-tier flexible capacity raises admitted load by **45.0%** over a firm-only benchmark. [Tapestry](https://www.tapestryenergy.com/ "Tapestry: a Google X project building AI tools and a shared model of the electric grid.")’s [HyperQ](https://www.tapestryenergy.com/en/projects/field-notes-hyperq-deployment-in-pjm-s-cycle-1 "HyperQ: Tapestry’s AI tool for accelerating interconnection application review, starting with site-control screening.") screened [site-control](https://www.pjm.com/ "Site control: legal proof that a developer has the right to build on a specific parcel, required before a generation project enters an interconnection study.") filings for 220 GW of [PJM](https://www.pjm.com/ "PJM Interconnection: regional grid operator and wholesale market for 13 eastern US states and Washington, DC.") Cycle 1 applications in under a day.

![Vendor-stated time windows for Ampt and LiLic](fig-storage-timescales.png){: w="1440" h="585" }
_Figure 1. Vendor-stated response or support windows. Ampt quotes a converter response under 1 ms; Vision quotes 1 MW for at least 60 s (and microsecond-scale transients). The EnerSys DataSafe Noir bar (600 kW / 5 min at end of life) is shown only as a timescale comparison; it is not a lead item today. These are claims, not independent tests._

## Key developments

### 1. Ampt’s 80 kW battery converter claims a sub-millisecond path from a shared battery bus to 800 VDC · Nov 11 2026 · industry / facility-to-rack power

Ampt, a DC-converter vendor from the solar-plus-storage world, announced a rack-mount 2U [Battery Converter](https://www.ampt.com/batteryconverter/ "Ampt Battery Converter: 2U, 80 kW (100 A) DC-DC unit that holds a regulated 800 VDC output from a shared battery/grid DC bus.") that delivers 80 kW (100 A) of regulated 800 VDC from a DC bus shared by batteries and grid or on-site generation. Units can be paralleled from one rack to a row or a hall. The company says the converter responds to GPU load changes in less than 1 millisecond, so the battery can supply or absorb the difference while the grid connection is sized for average rather than peak load. It also says GPUs can then “run without power capping.” Partner pilots are underway; general availability is set for Q3 2027.

The electrical idea is a higher-voltage DC trunk. The battery bus runs at 1100–1500 VDC, following state of charge; the converter holds 800 VDC at the rack. Stored energy stays DC, avoiding an AC-coupled round trip. Peak converter efficiency is stated as 99.2%, using MOSFET rather than IGBT switching. With a [grid-forming](https://en.wikipedia.org/wiki/Grid-forming "Grid-forming: inverter control that sets voltage and frequency, so a battery plant can support the grid rather than only follow it.") [power conversion system](https://en.wikipedia.org/wiki/Power_conditioner "Power conversion system, PCS: the inverters and controls that couple a battery or DC bus to the AC grid or to a facility DC bus.") on the grid side, the same battery can also support voltage and frequency. On redundancy, Ampt says an N+1 set of 80 kW blocks on a 1.5 MW GPU rack needs about 5% extra installed capacity, versus 100% extra for a redundant MW-class converter.

**Caveats.** This is a product launch, not a measured field result. Sub-millisecond response, 99.2% peak efficiency, and “no power capping” are vendor claims. The converter is not the energy store; the battery and the grid-side PCS still have to be sized for the step. General availability is three quarters away.

**Implication.** This is a facility-edge answer to the same problem as rack [BBUs](https://www.opencompute.org/ "Battery backup unit: a rack-level battery shelf that rides through short outages and can buffer load steps.") and GPU caps: present a steadier load at the point of interconnection so the operator can oversubscribe the grid connection. If the claim holds, the oversubscription decision moves from “how hard can I cap the GPU” to “how much average-versus-peak the battery is allowed to cover.”

- [Ampt / PR Newswire: Sub-Millisecond Battery Converter (Nov 11 2026)](https://www.prnewswire.com/news-releases/sub-millisecond-battery-converter-gives-800-vdc-ai-data-centers-more-compute-from-the-same-grid-connection-302935719.html)
- [Ampt Battery Converter product page](https://www.ampt.com/batteryconverter/)

### 2. Vision Group’s LiLic sidecar: 1 MW for at least 60 seconds, LIC plus LFP, in the white space · Nov 11 2026 · industry / rack-level smoothing and backup

Vision Group used the US YOTTA 2026 show to debut LiLic, an 800 VDC “hybrid power sidecar” meant to sit in the data-hall white space next to compute racks. The cabinet combines [lithium-ion capacitors](https://en.wikipedia.org/wiki/Lithium-ion_capacitor "Lithium-ion capacitor, LIC: a hybrid device between a supercapacitor and a lithium battery, used for high-power, short-duration pulses.") (LIC) for high-frequency pulses with [lithium iron phosphate](https://en.wikipedia.org/wiki/Lithium_iron_phosphate_battery "Lithium iron phosphate, LFP: a lithium-ion chemistry used for stationary storage and backup because of cycle life and thermal stability.") (LFP) for short backup. The stated rating is 1 MW of discharge and at least 60 seconds of backup at a 1 MW load.

The company says the same cabinet can cover microsecond-scale transients at the GPU and [VRM](https://en.wikipedia.org/wiki/Voltage_regulator_module "Voltage regulator module: the multiphase point-of-load converter that feeds the processor core rail.") as well as lower-frequency swings from large training jobs, and can ride through a brief upstream disturbance. It connects directly to an 800 VDC bus, including in halls that use a [solid-state transformer](https://en.wikipedia.org/wiki/Solid-state_transformer "Solid-state transformer, SST: a power-electronic transformer that can convert medium-voltage AC directly to a DC bus such as 800 V.") (SST). The integrated stack is described as bidirectional [silicon-carbide](https://en.wikipedia.org/wiki/Silicon_carbide "Silicon carbide, SiC: a wide-bandgap semiconductor used in high-voltage, high-efficiency power converters.") (SiC) DC-DC conversion, a battery management system, microsecond-class hardware [e-Fuse](https://en.wikipedia.org/wiki/Electronic_fuse "Electronic fuse, e-Fuse: a semiconductor protection device that interrupts current much faster than a mechanical breaker.") protection, liquid cooling and hot-swappable modules.

**Caveats.** Vendor announcement, no datasheet numbers for efficiency, cycle life, or measured step-load response, and no independent test. “Microsecond-scale” transients and “at least 60 seconds” are company figures.

**Implication.** LiLic sits closer to the rack than Ampt’s bus converter and quotes both a power and an energy number. One MW for 60 s is about 16.7 kWh (see Spotlight). That is enough to hold a 1 MW step while a slower facility battery or a software cap ramp engages.

- [Vision Group: Beyond Backup — LiLic megawatt-class power support (Nov 11 2026)](https://www.vision-batt.com/en/news/show/post-262.html)

### 3. BNEF: 181 GW of announced on-site gas; data-center demand 2,354 TWh by 2035; Microsoft says it will pay its own way · Nov 11 2026 · industry / grid and behind-the-meter generation

BNEF’s public note *Powering the Data Center Boom*, dated Nov 11, says data-center electricity demand is set to almost quadruple to **2,354 TWh by 2035**, equivalent to **7%** of global electricity demand. It has tracked **181 GW** of announced gas-fired generation proposed alongside data centers, with **more than 90%** in the United States. The note is explicit that “the announced pipeline varies widely in maturity and timing and should be viewed as an indication of potential scale rather than a forecast of what will ultimately be built.” If all announced US on-site gas plants were built and operated at BNEF’s assumptions, they would emit about **345 million metric tons of CO2e a year**, **152 MtCO2e** more than if the associated data-center capacity were served by average US grid electricity, or **10%** of US power-sector emissions in 2025. BNEF also warns that even where on-site gas is described as temporary while a grid connection is pending, “the economics could encourage them to continue generating.”

The same day, at BNEF’s Houston conference, Noelle Walsh, Microsoft’s president of cloud operations and innovation, said the company aims to power its data centers without relying on government subsidies or raising costs for other electricity customers: “We don’t want other customers to be paying for our growth.” And: “We will pay our own way.” Those remarks are from a [Bloomberg Law](https://news.bloomberglaw.com/artificial-intelligence/microsoft-vows-to-pay-its-own-way-to-power-data-centers "Bloomberg Law, Nov 11 2026: Microsoft Vows to Pay Its Own Way to Power Data Centers.") lead; they are a cost-allocation pledge, not a named tariff or megawatt commitment.

**Caveats.** The BNEF report was commissioned by Bloomberg Philanthropies. The 345 / 152 / 10% figures are a “if all announced” scenario, not an emissions forecast. The full report is client-only. Walsh’s comments are remarks, not a filing.

**Implication.** On-site gas is being sized to unsmoothed peak and to interconnection delay. A hall that can present a smoother, more curtailable load is more likely to take a faster grid path and less likely to lock in a permanent plant. “Pay our own way” is the political counterpart: who pays for the peak is now a first-party hyperscaler talking point.

- [BNEF: Data Center Power Demand Is Set to Surge (Nov 11 2026)](https://about.bnef.com/insights/data-centers/data-center-power-demand-is-set-to-surge-raising-new-climate-challenges-bloombergnef/)
- [Bloomberg Law: Microsoft Vows to Pay Its Own Way to Power Data Centers (Nov 11 2026)](https://news.bloomberglaw.com/artificial-intelligence/microsoft-vows-to-pay-its-own-way-to-power-data-centers)

### 4. Constellation’s first Peak+ contract: 270 MW, 20 years, nuclear energy plus new capacity from 2028 · Nov 9–11 2026 · industry / grid supply

In its third-quarter results (Nov 9), Constellation said it had signed a 20-year agreement for 270 MW of “unit-contingent energy, capacity, and attributes from our existing nuclear fleet,” beginning in 2028. It is the first transaction under Peak+, which the company describes as an integrated solution that “brings together new capacity, including new generation and [demand response](https://en.wikipedia.org/wiki/Demand_response "Demand response, DR: a large customer cuts or shifts load when the grid is stressed, in exchange for payment or a better interconnection deal."), with energy products.” The customer is not named. CEO Joe Dominguez framed Peak+ as a way to pair the existing fleet with incremental capacity — batteries, generation on land around the plants, and demand response — as an alternative to new gas plants. A Nov 11 [Utility Dive](https://www.utilitydive.com/news/constellation-pursues-hybrid-nuclearcapacity-contracts-alongside-uprates/874408/ "Utility Dive report, Nov 11 2026, on Constellation’s Peak+ earnings-call remarks.") write-up covers the earnings-call remarks.

**Caveats.** Unit-contingent supply is only as good as the unit. The “new capacity” leg is a product description, not a named battery or DR megawatt figure in the release.

**Implication.** This is a “bring your own firm capacity” offer that still starts from the existing nuclear fleet, rather than a behind-the-meter gas island. For a campus that can offer demand response, the Peak+ wrapper is another place where a trusted cap and a bounded rebound ramp become commercial terms.

- [Constellation: Third Quarter 2026 results (Nov 9 2026)](https://www.constellationenergy.com/news/2026/11/constellation-reports-third-quarter-2026-results.html)
- [Utility Dive: Constellation pursues hybrid capacity contracts (Nov 11 2026)](https://www.utilitydive.com/news/constellation-pursues-hybrid-nuclearcapacity-contracts-alongside-uprates/874408/)

### 5. A 1 MW / 1 MWh battery, trained on the scheduling cost, cuts mean grid-import ramps 71.70% · arXiv Nov 10 (announced Nov 11) · academia / ramp smoothing

Zheng, Jiang, de Nijs, Lam and Wagner (Monash) treat AI-facility swings as a grid-import problem and schedule a behind-the-meter BESS without changing compute. The controller is a rolling-horizon, two-stage stochastic program on one-minute steps over a 60-minute horizon: it commits baseline battery power and reserves, then dispatches against demand scenarios, with operating cost, grid-ramp penalties and [CVaR](https://en.wikipedia.org/wiki/Expected_shortfall "Conditional value-at-risk, CVaR: the expected loss in the worst fraction of outcomes, used here as a risk term on cost and ramps."). They train a constraint-aware neural optimization layer ([BS-DFL](https://arxiv.org/abs/2611.13694 "Battery scheduling decision-focused learning: a neural optimization layer trained on the scheduling objective rather than on forecast error.")) directly on that objective, then freeze it to train the demand predictor, so the controller can run without a solver at decision time.

The test is a 10,000-minute simulation on 10 MW, 2,840-node AI facility profiles derived from measured workloads, with a **1 MW / 1 MWh** BESS (10–90% [SOC](https://en.wikipedia.org/wiki/State_of_charge "State of charge: the fraction of a battery’s energy capacity that is currently stored."), 50% initial and target). Versus an MSE-trained predictor plus a Gurobi mixed-integer solver, BS-DFL cuts mean absolute minute-to-minute grid-import change by **71.70%** (0.9988 kW versus 3.5293 kW) and total scheduling cost by **18.01%**. Mean decision time is **18.77 ms**, versus 2,513.41 ms for the solver path. Total cost is within 4.39% of a perfect-information rolling-horizon reference. The 95th-percentile change is 0.0104 kW — nearly flat import most of the time — though the maximum change is still 203.920 kW. Forecast MAE is actually worse than the MSE baseline (240.66 versus 179.97 kW); that is the point of training on decisions rather than forecast error.

**Caveats.** Simulation only. The residual ramps in Table I are in kilowatts on a 10 MW profile, not a GW campus. Costs are in unspecified “CU.” The source traces are constructed facility profiles, not a named public dataset in the abstract.

**Implication.** This is the cleanest new academic result on facility-side ramp smoothing: hold the compute schedule fixed and spend a 1-hour battery (1 MWh at 1 MW) at the point of interconnection. It complements yesterday’s checkpoint-fill paper, which reshaped compute instead. The 18.77 ms controller is in the same time band as a real PCS set-point.

- [arXiv 2611.13694: Battery-Assisted Grid-Import Smoothing in AI Data Centers](https://arxiv.org/abs/2611.13694)

### 6. Meta at HPCA 2027: planning, validating and dimming a 160 MW, 83K-GB200 cluster · conference PDF posted Nov 9 · academia / training power capping

Ardestani et al. (Meta) report the full power-management lifecycle for a **160 MW** cluster of **83K GB200** GPUs, spanning five halls: planning GPU limits and cluster size before hardware arrives; post-deployment validation; and runtime control ([Dimmer](https://arxiv.org/abs/2605.24461 "Dimmer: Meta’s runtime power controller, previously described in the Dynamo Dimmer preprint, that caps jobs by priority to clear device-level power overages.")). Relative to a counterfactual **1200 W TDP** design, planning at a **960 W** GPU power limit “projects 6.6% higher aggregate throughput.” Deployment measurements “support a further 1–2% gain at 1020 W,” and “production telemetry indicates that Dimmer’s 1120 W operating point provides an additional estimated 2–4%.” Compounded, “these contributions correspond to an estimated 10–13% improvement.” The authors call this the first reported hyperscale GPU deployment that uses a sub-TDP limit to optimize cluster-level performance per watt, and note that NVIDIA later introduced MAX-Q and MAX-P profiles for [GB300](https://www.nvidia.com/en-us/data-center/gb300-nvl72/ "NVIDIA GB300: the generation after GB200, for which NVIDIA published Max-Q and Max-P power profiles.").

Production lessons matter as much as the headline number. The power hierarchy is oversubscribed — downstream nameplate can exceed an upstream device rating — and static headroom fragmentation “leaves up to 10% of power stranded.” PSU telemetry systematically overestimates rack power and has to be calibrated. Three-phase current imbalance triggers capping below the aggregate device limit. Under-torqued 12 V busbar screws caused GPUs to over-report power, firmware-throttle, and become stragglers that pace synchronous training; Dimmer then raises limits on those jobs rather than dragging the whole run. The focus is synchronous pre-training, “the hardest case”; the authors say the planning method “also applies to inference with a different per-GPU performance curve, and we have used it there.” This is a material follow-on to the Dimmer / 100 MW-scale preprint already in the Nov 3 shortlist, now with a 160 MW cluster, staged 960 / 1020 / 1120 W limits, and compounded 10–13% estimates.

**Caveats.** Several gains are projected or estimated, not a single measured A/B test. Training is the evaluation focus. The paper says production traces (oscilloscope, PSU and [DCIM](https://en.wikipedia.org/wiki/Data_center_infrastructure_management "Data center infrastructure management: software that records facility power, cooling and IT telemetry.")) will be released; a GitHub path named in the PDF returned HTTP 404 when checked on Nov 12.

**Implication.** The usable oversubscription stack at hyperscale is a chain: pick a sub-TDP planning cap so more GPUs fit in the 160 MW envelope, validate once the iron is in, then let a runtime dimmer recover stranded watts and protect training jobs. Phase imbalance and bad mechanical joints are first-class power-budget bugs. Inference can reuse the planning curve; it is not the measured object here.

- [HPCA 2027 PDF: End-to-End Power Management for a 160 MW AI Datacenter](https://aisystemcodesign.github.io/papers/HPCA27-AI-Cluster-Power.pdf)
- [Related preprint, arXiv 2605.24461 (Dimmer / 100 MW-scale)](https://arxiv.org/abs/2605.24461)

### 7. KAIROS, revised: context-aware caps cut agentic inference power 27% on one GPU and 46.3% on four · arXiv v2 Nov 10 (announced Nov 11) · academia / inference power capping

Yuan, Chowdhury and Talati argue that power managers built for single-turn [LLM](https://en.wikipedia.org/wiki/Large_language_model "Large language model: a transformer model used for text generation and, increasingly, tool-using agents.") serving misfire on [agentic](https://en.wikipedia.org/wiki/Intelligent_agent "Agentic AI: a workload in which a model issues many tool-interleaved, stateful calls for one user task, so context grows across turns.") work. Each request carries long-lived context that grows across tool calls. Lowering GPU frequency can push the system into a memory-thrashing regime that hurts both throughput and power. KAIROS treats agent context as a first-class signal and jointly sets GPU frequency, per-instance concurrency, and placement across instances.

The revised paper (v2, Nov 10) evaluates replayed agent traces for 3 hours on an H100 NVL server (400 W TDP) running [vLLM](https://docs.vllm.ai/ "vLLM: an open-source high-throughput LLM serving engine.") 0.14.0 with Qwen3-Coder-30B in FP8, plus checks on Ministral-3-14B and a Claude Code harness. Workloads are [SWE-Bench Verified](https://www.swebench.com/ "SWE-Bench Verified: a human-validated subset of GitHub-issue fixing tasks used to test coding agents."), DABStep and Terminal-Bench 2.0. Frequency and power are controlled with [Zeus](https://ml.energy/zeus/ "Zeus: a software stack for measuring and capping GPU energy and power."). On a single instance, against no frequency control and a 20 token/s per-agent P5 throughput [SLO](https://en.wikipedia.org/wiki/Service-level_objective "Service-level objective: a measurable performance target, here P5 per-agent output throughput."), KAIROS saves **27% power on average, up to 39.8%**, and meets the SLO; a fixed 810 MHz cap saves more power but misses the SLO. Across four instances at 0.16 jobs/s, average power falls from 1279.5 W with no control to 784.8 W with KAIROS plus round-robin routing, and to **686.5 W** with context-aware routing — a **46.3%** cut. P5 throughput is 26.9 token/s versus 25.4 token/s under round-robin.

**Caveats.** Results are from deterministic replays of recorded traces, not a live multi-tenant cluster. Each vLLM instance uses one H100; prefill–decode disaggregation is not used. The 46.3% figure is one four-GPU point at one arrival rate. The paper first appeared in April; today’s hook is the Nov 10 revision, announced on Nov 11.

**Implication.** Agentic inference is not a softer version of decode capping. Frequency and admission have to track context growth, or a cap creates thrashing that wastes the watts you were trying to reclaim. Placement is also a power lever: consolidating work lets some GPUs sit near idle. That is usable headroom for oversubscription, but only if the SLO is defined per agent.

![KAIROS four-instance power comparison](fig-kairos-power.png){: w="1440" h="585" }
_Figure 2. Average power of four H100 instances at 0.16 jobs/s, from KAIROS §8.3. Context-aware routing reaches 686.5 W, 46.3% below the uncontrolled 1279.5 W._

- [arXiv 2604.16682v2: KAIROS (revised Nov 10 2026)](https://arxiv.org/abs/2604.16682)
- [HTML version](https://arxiv.org/html/2604.16682v2)

### 8. Firm plus flexible tiers admit 45.0% more large-load capacity than firm-only service · arXiv Nov 10 (announced Nov 11) · academia / grid interconnection

Li, Fang, Chen (Dartmouth) and Qin (Purdue) ask how much extra load a transmission network can accept if some of it is flexible. Firm capacity must be served under all planning conditions. Flexible tiers may be curtailed within agreed depth and probability limits, with a two-layer priority rule for sharing curtailment. The authors write a mixed-integer chance-constrained model, then an equivalent aggregate form that drops individual curtailment variables and priority binaries without changing the feasible capacity set.

The introduction names AI data centers as a driver and cites FERC co-location and PJM curtailment-priority proposals. On the IEEE RTS 73-bus system, three data centers (buses 103, 214 and 319) each request up to 400 MW firm and 200 MW per flexible tier. All three firm requests are awarded in full, and total admitted capacity is **1,883.5 MW**, **45.0%** above the **1,298.8 MW** firm-only benchmark on the same demand trajectories. In-sample exceedance rates on a PJM 5-bus case stay below the stated QoS limits.

**Caveats.** Planning-model results on test systems, not an actual interconnection queue. Chance constraints in the quoted table are in-sample. The paper does not model ramp rates or intra-hour transients.

**Implication.** This is the formal counterpart of “grid access in exchange for certainty.” The extra 45% is only usable if the campus can actually shed the flexible tier — with a cap, a battery, or deferred work — when the operator calls. Items 1, 2, 5 and 7 are how you would make that promise real.

- [arXiv 2611.13673: Priority-Aware Firm and Flexible Capacity for Large-Load Interconnection](https://arxiv.org/abs/2611.13673)

### 9. Tapestry’s HyperQ screens 220 GW of PJM Cycle 1 site-control filings in under a day · Nov 11 2026 · adjacent / interconnection process

Tapestry reports the first operational use of HyperQ on PJM’s reformed Cycle 1 interconnection window. The tool reviewed site-control documentation for **811 generation applications, representing 220 GW**, and produced citation-backed readiness reports with a median runtime of 6 minutes 15 seconds. Tapestry compares that with a two-month manual timeline and calls it a 60× acceleration, with reports delivered overnight. Every assessment links to a page, clause or coordinate in the source filing. PJM, which keeps final compliance decisions, said the preliminary results “demonstrate a repeatable model for how AI can operate reliably under strict human governance” and a basis for its target 12-month interconnection timeline.

Tapestry is explicit about scope: these figures cover initial site-control review, not power-flow, stability or short-circuit studies.

**Caveats.** The 60× and “under a day” figures are Tapestry’s comparison with a manual baseline, not a PJM-audited productivity study. This is about generation queues, not large-load queues.

**Implication.** Faster generation interconnection is one of the few ways to grow the firm supply that AI campuses are trying to contract (items 3 and 4). It does not relax a ramp limit at the campus fence.

- [Tapestry: Field Notes — HyperQ deployment in PJM’s Cycle 1](https://www.tapestryenergy.com/en/projects/field-notes-hyperq-deployment-in-pjm-s-cycle-1)

## Spotlight: a 1 MW, 60-second hold is only 16.7 kWh

A converter can be fast and still store almost no energy. The energy that actually covers a step is

$$
E = P \times T.
$$

Vision’s stated LiLic rating — 1 MW for at least 60 seconds — is

$$
E = 1\,\mathrm{MW} \times 60\,\mathrm{s} = 16.7\,\mathrm{kWh}.
$$

Ampt’s own description of AI racks swinging between 30% and 100% of nameplate is a 0.7 MW step on a 1 MW rack. Held for the same 60 seconds, that is 11.7 kWh. The Monash study (item 5) uses a **1 MW / 1 MWh** facility battery — 60 times that 16.7 kWh — behind a 10 MW profile, which is why it can hold import almost flat for minutes rather than seconds.

![Energy in a 60-second hold at 1 MW and 0.7 MW](fig-hold-energy.png){: w="1440" h="555" }
_Figure 3. Illustration, not a measurement. Energy in a rectangular 60-second hold at 1 MW (16.7 kWh) and at 0.7 MW (11.7 kWh)._

The practical split is then: use a sub-millisecond converter or LIC stage so the grid never sees the edge of the step; size a minute-scale sidecar or a 1-hour facility battery for the energy; leave software caps (items 6 and 7) for the part you would rather not store. Mixing those ratings in one line item is how rooms get over- or under-built.

## Bottom line

Nov 11 produced a clear hardware pair for 800 VDC smoothing: a sub-millisecond bus converter (Ampt, GA Q3 2027) and a 1 MW / 60 s white-space sidecar (Vision). Both are vendor claims, but they name the two quantities that matter — response time and stored energy. BNEF puts a number on the alternative: 181 GW of announced on-site gas, to be read as a pipeline, while Microsoft says it will pay its own way. The research side is unusually direct today. A 1 MW / 1 MWh battery, trained on the scheduling cost, cuts mean import ramps 71.70% in simulation. Meta’s 160 MW production paper shows what a real cap stack looks like from planning at 960 W through Dimmer at 1120 W, with an estimated 10–13% throughput gain and up to 10% of power stranded by placement and phase imbalance. KAIROS extends that logic to agentic inference, and the Dartmouth–Purdue paper shows a 45% interconnection bonus if the flexible tier is real. The next design question is still the one in the Spotlight: how many milliseconds, and how many kilowatt-hours, you are actually buying.

## Glossary

- [**800 VDC**](https://www.nvidia.com/en-us/data-center/technologies/800-vdc-architecture/): Facility or row distribution at 800 V DC.
- [**BESS**](https://en.wikipedia.org/wiki/Battery_storage_power_station): Battery energy storage system.
- [**BBU**](https://www.opencompute.org/): Rack-level battery backup unit.
- [**BNEF**](https://about.bnef.com/): BloombergNEF, Bloomberg’s energy-research arm.
- [**CVaR**](https://en.wikipedia.org/wiki/Expected_shortfall): Conditional value-at-risk.
- [**Demand response**](https://en.wikipedia.org/wiki/Demand_response): Cutting or shifting load when the grid asks.
- [**Dimmer**](https://arxiv.org/abs/2605.24461): Meta’s runtime power controller for clearing device-level overages.
- [**e-Fuse**](https://en.wikipedia.org/wiki/Electronic_fuse): Semiconductor over-current protection.
- [**GB200**](https://www.nvidia.com/en-us/data-center/gb200-nvl72/): NVIDIA Blackwell GPU used in NVL72 racks.
- [**Grid-forming**](https://en.wikipedia.org/wiki/Grid-forming): Inverter control that sets voltage and frequency.
- [**H100**](https://www.nvidia.com/en-us/data-center/h100/): NVIDIA Hopper data-center GPU.
- [**HPCA**](https://hpca-conf.org/): International Symposium on High-Performance Computer Architecture.
- [**LFP**](https://en.wikipedia.org/wiki/Lithium_iron_phosphate_battery): Lithium iron-phosphate battery chemistry.
- [**LIC**](https://en.wikipedia.org/wiki/Lithium-ion_capacitor): Lithium-ion capacitor.
- [**PCS**](https://en.wikipedia.org/wiki/Power_conditioner): Power conversion system.
- [**Peak+**](https://www.constellationenergy.com/news/2026/11/constellation-reports-third-quarter-2026-results.html): Constellation product pairing existing nuclear energy with new capacity and demand response.
- [**PJM**](https://www.pjm.com/): Mid-Atlantic and Midwest grid operator.
- [**SiC**](https://en.wikipedia.org/wiki/Silicon_carbide): Silicon carbide.
- [**Sidecar**](https://lizhouyu.github.io/technical_posts/posts/800v-dc-goes-live-calibrated-decode-caps/): A power rack next to the IT racks, often converting to 800 VDC.
- [**SLO**](https://en.wikipedia.org/wiki/Service-level_objective): Service-level objective.
- [**SOC**](https://en.wikipedia.org/wiki/State_of_charge): Battery state of charge.
- [**SST**](https://en.wikipedia.org/wiki/Solid-state_transformer): Solid-state transformer.
- [**TDP**](https://en.wikipedia.org/wiki/Thermal_design_power): Thermal design power, the vendor’s hardware design rating.
- [**vLLM**](https://docs.vllm.ai/): Open-source LLM serving engine.
- [**VRM**](https://en.wikipedia.org/wiki/Voltage_regulator_module): Voltage regulator module at the point of load.

---

_How useful was today's brief? Reply in Grok Bot chat with an overall rating (1–5) and, if you like, per-item ratings (1–5)._
