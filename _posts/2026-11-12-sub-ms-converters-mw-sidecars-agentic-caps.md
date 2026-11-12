---
title: "Sub-ms 800 VDC converters; a 1 MW sidecar; agentic power caps"
date: 2026-11-12 08:30:00 +0800
categories: [Daily Brief, Power]
tags: [800vdc, ramp-smoothing, energy-storage, power-capping, inference, dvfs, grid, industry, academia, adjacent]
description: "Ampt launches an 80 kW, sub-millisecond battery converter that feeds regulated 800 VDC from a shared battery bus, aiming for general availability in Q3 2027. Vision Group's LiLic sidecar rates 1 MW for at least 60 seconds with a lithium-ion capacitor plus LFP stack. Constellation signs a first 20-year, 270 MW Peak+ deal from its nuclear fleet, starting in 2028. EnerSys books a first order for DataSafe Noir, a 600 kW / 5 min lithium UPS cabinet. A revised KAIROS paper cuts agentic inference power 27% on one GPU and 46.3% across four. StepSplit attributes batch energy with 0.4–6.4% error. Tapestry's HyperQ screens 220 GW of PJM Cycle 1 site-control filings in under a day. Delta shows an 800 VDC, 2.5 MW in-row coolant unit at SC26."
media_subpath: /assets/img/briefs/2026-11-12/
image:
  path: fig-storage-timescales.png
  alt: Vendor-stated time windows for Ampt’s sub-millisecond 800 VDC converter, Vision’s 1 MW / 60 s LiLic sidecar, and EnerSys DataSafe Noir’s 600 kW / 5 min UPS cabinet
math: true
---

## At a glance

Two new [800 VDC](https://www.nvidia.com/en-us/data-center/technologies/800-vdc-architecture/ "800 VDC: distributing power to AI racks at 800 V direct current instead of 54 V DC in-rack or low-voltage AC, which cuts current and copper for 100 kW to 1 MW racks.") products landed on Nov 11. [Ampt](https://www.ampt.com/ "Ampt: Fort Collins company whose DC optimizers and converters have been used in utility-scale solar and storage; it is now offering an 800 VDC battery converter for AI data centers.") announced an 80 kW, 2U battery converter that takes a shared 1100–1500 VDC battery bus down to regulated 800 VDC and claims a response to [GPU](https://en.wikipedia.org/wiki/Graphics_processing_unit "Graphics processing unit: the accelerator that dominates AI-rack power.") load changes in less than 1 millisecond, with general availability in Q3 2027. [Vision Group](https://www.vision-batt.com/en/ "Vision Group: battery manufacturer offering lithium and hybrid storage products, including data-center backup and 800 VDC white-space systems.") introduced [LiLic](https://www.vision-batt.com/en/news/show/post-262.html "LiLic: Vision Group’s 800 VDC hybrid power sidecar combining lithium-ion capacitors with LFP batteries for smoothing and short backup."), a white-space sidecar rated at 1 MW for at least 60 seconds. [Constellation](https://www.constellationenergy.com/ "Constellation Energy: US generator and retail supplier with the largest nuclear fleet in the country, much of it in PJM.") signed its first [Peak+](https://www.constellationenergy.com/news/2026/11/constellation-reports-third-quarter-2026-results.html "Peak+: Constellation’s product that pairs energy from the existing nuclear fleet with new capacity, including new generation and demand response.") contract: 270 MW of unit-contingent nuclear energy, capacity and attributes for 20 years, starting in 2028. [EnerSys](https://www.enersys.com/ "EnerSys: US maker of industrial batteries and stored-energy systems, including data-center UPS batteries.") reported a first order for [DataSafe Noir](https://www.enersys.com/en/products/batteries/datasafe/datasafe-noir/ "DataSafe Noir: EnerSys lithium iron-phosphate UPS energy-storage cabinet, rated up to 600 kW for 5 minutes at end of life."), a 600 kW / 5 min lithium [UPS](https://en.wikipedia.org/wiki/Uninterruptible_power_supply "Uninterruptible power supply: batteries plus power electronics that carry the IT load through a grid disturbance.") cabinet.

On the research side, a Nov 10 revision of [KAIROS](https://arxiv.org/abs/2604.16682 "KAIROS: context-aware power manager for agentic LLM serving that jointly sets GPU frequency, concurrency and placement.") (arXiv 2604.16682v2) reports a 27% average (up to 39.8%) power cut on a single [H100](https://www.nvidia.com/en-us/data-center/h100/ "NVIDIA H100: Hopper-generation data-center GPU; the KAIROS server uses H100 NVL parts with a 400 W TDP.") and 46.3% across four instances, without missing a 20 token/s per-agent [SLO](https://en.wikipedia.org/wiki/Service-level_objective "Service-level objective: a measurable performance target, here P5 per-agent output throughput."). [StepSplit](https://arxiv.org/abs/2611.13802 "StepSplit: a closed-form Shapley method that attributes a batched GPU’s energy to individual LLM requests.") (arXiv 2611.13802) attributes batch energy to requests with 0.4–6.4% error versus a token-proportional baseline that can miss by more than 60%. [Tapestry](https://www.tapestryenergy.com/ "Tapestry: a Google X project building AI tools and a shared model of the electric grid.")’s [HyperQ](https://www.tapestryenergy.com/en/projects/field-notes-hyperq-deployment-in-pjm-s-cycle-1 "HyperQ: Tapestry’s AI tool for accelerating interconnection application review, starting with site-control screening.") screened [site-control](https://www.pjm.com/ "Site control: legal proof that a developer has the right to build on a specific parcel, required before a generation project enters an interconnection study.") filings for 220 GW of [PJM](https://www.pjm.com/ "PJM Interconnection: regional grid operator and wholesale market for 13 eastern US states and Washington, DC.") Cycle 1 applications in under a day. [Delta](https://www.deltaww.com/ "Delta Electronics: Taiwanese power-electronics and thermal-management company with a large data-center cooling and power portfolio.") will show an 800 VDC, 2.5 MW in-row [CDU](https://en.wikipedia.org/wiki/Liquid_cooling "Coolant distribution unit: a skid that pumps and conditions liquid coolant for a row or hall of IT racks.") at [SC26](https://sc26.supercomputing.org/ "SC26: the International Conference for High Performance Computing, Networking, Storage, and Analysis, in Chicago, 17–19 Nov 2026.").

![Vendor-stated time windows for Ampt, LiLic and DataSafe Noir](fig-storage-timescales.png){: w="1440" h="585" }
_Figure 1. Vendor-stated response or support windows. Ampt quotes a converter response under 1 ms; Vision quotes 1 MW for at least 60 s (and microsecond-scale transients); EnerSys rates DataSafe Noir at 600 kW for 5 minutes at end of life. These are claims, not independent tests._

## Key developments

### 1. Ampt’s 80 kW battery converter claims a sub-millisecond path from a shared battery bus to 800 VDC · Nov 11 2026 · industry / facility-to-rack power

Ampt, a DC-converter vendor from the solar-plus-storage world, announced a rack-mount 2U [Battery Converter](https://www.ampt.com/batteryconverter/ "Ampt Battery Converter: 2U, 80 kW (100 A) DC-DC unit that holds a regulated 800 VDC output from a shared battery/grid DC bus.") that delivers 80 kW (100 A) of regulated 800 VDC from a DC bus shared by batteries and grid or on-site generation. Units can be paralleled from one rack to a row or a hall. The company says the converter responds to GPU load changes in less than 1 millisecond, so the battery can supply or absorb the difference while the grid connection is sized for average rather than peak load. It also says GPUs can then “run without power capping.” Partner pilots are underway; general availability is set for Q3 2027.

The electrical idea is a higher-voltage DC trunk. The battery bus runs at 1100–1500 VDC, following state of charge; the converter holds 800 VDC at the rack. Stored energy stays DC, avoiding an AC-coupled round trip. Peak converter efficiency is stated as 99.2%, using MOSFET rather than IGBT switching. With a [grid-forming](https://en.wikipedia.org/wiki/Grid-forming "Grid-forming: inverter control that sets voltage and frequency, so a battery plant can support the grid rather than only follow it.") [power conversion system](https://en.wikipedia.org/wiki/Power_conditioner "Power conversion system, PCS: the inverters and controls that couple a battery or DC bus to the AC grid or to a facility DC bus.") on the grid side, the same battery can also support voltage and frequency. On redundancy, Ampt says an N+1 set of 80 kW blocks on a 1.5 MW GPU rack needs about 5% extra installed capacity, versus 100% extra for a redundant MW-class converter. Sites with solar can attach [PV](https://en.wikipedia.org/wiki/Photovoltaics "Photovoltaic: solar generation that produces DC, which can be coupled to a battery bus without an extra inverter if the voltages match.") strings to the same bus through Ampt String Optimizers.

**Caveats.** This is a product launch, not a measured field result. Sub-millisecond response, 99.2% peak efficiency, and “no power capping” are vendor claims. The converter is not the energy store; the battery and the grid-side PCS still have to be sized for the step. General availability is three quarters away.

**Implication.** This is a facility-edge answer to the same problem as rack [BBUs](https://www.opencompute.org/ "Battery backup unit: a rack-level battery shelf that rides through short outages and can buffer load steps.") and GPU caps: present a steadier load at the point of interconnection so the operator can oversubscribe the grid connection. It competes with, rather than replaces, software caps. If the claim holds, the oversubscription decision moves from “how hard can I cap the GPU” to “how much average-versus-peak the battery is allowed to cover.”

- [Ampt / PR Newswire: Sub-Millisecond Battery Converter (Nov 11 2026)](https://www.prnewswire.com/news-releases/sub-millisecond-battery-converter-gives-800-vdc-ai-data-centers-more-compute-from-the-same-grid-connection-302935719.html)
- [Ampt Battery Converter product page](https://www.ampt.com/batteryconverter/)

### 2. Vision Group’s LiLic sidecar: 1 MW for at least 60 seconds, LIC plus LFP, in the white space · Nov 11 2026 · industry / rack-level smoothing and backup

Vision Group used the US YOTTA 2026 show to debut LiLic, an 800 VDC “hybrid power sidecar” meant to sit in the data-hall white space next to compute racks. The cabinet combines [lithium-ion capacitors](https://en.wikipedia.org/wiki/Lithium-ion_capacitor "Lithium-ion capacitor, LIC: a hybrid device between a supercapacitor and a lithium battery, used for high-power, short-duration pulses.") (LIC) for high-frequency pulses with [lithium iron phosphate](https://en.wikipedia.org/wiki/Lithium_iron_phosphate_battery "Lithium iron phosphate, LFP: a lithium-ion chemistry used for stationary storage and backup because of cycle life and thermal stability.") (LFP) for short backup. The stated rating is 1 MW of discharge and at least 60 seconds of backup at a 1 MW load.

The company says the same cabinet can cover microsecond-scale transients at the GPU and [VRM](https://en.wikipedia.org/wiki/Voltage_regulator_module "Voltage regulator module: the multiphase point-of-load converter that feeds the processor core rail.") as well as lower-frequency swings from large training jobs, and can ride through a brief upstream disturbance. It connects directly to an 800 VDC bus, including in halls that use a [solid-state transformer](https://en.wikipedia.org/wiki/Solid-state_transformer "Solid-state transformer, SST: a power-electronic transformer that can convert medium-voltage AC directly to a DC bus such as 800 V.") (SST). The integrated stack is described as bidirectional [silicon-carbide](https://en.wikipedia.org/wiki/Silicon_carbide "Silicon carbide, SiC: a wide-bandgap semiconductor used in high-voltage, high-efficiency power converters.") (SiC) DC-DC conversion, a battery management system, microsecond-class hardware [e-Fuse](https://en.wikipedia.org/wiki/Electronic_fuse "Electronic fuse, e-Fuse: a semiconductor protection device that interrupts current much faster than a mechanical breaker.") protection, liquid cooling and hot-swappable modules.

**Caveats.** Vendor announcement, no datasheet numbers for efficiency, cycle life, or measured step-load response, and no independent test. “Microsecond-scale” transients and “at least 60 seconds” are company figures. YOTTA debut is a showcase, not a fleet deployment.

**Implication.** LiLic sits closer to the rack than Ampt’s bus converter and quotes both a power and an energy number. One MW for 60 s is about 16.7 kWh (see Spotlight). That is enough to hold a 1 MW step while a slower facility battery or a software cap ramp engages, and it is a different product from a 5-minute UPS cabinet. Trip coordination and capacitive inrush on an 800 VDC bus remain open engineering items.

- [Vision Group: Beyond Backup — LiLic megawatt-class power support (Nov 11 2026)](https://www.vision-batt.com/en/news/show/post-262.html)

### 3. Constellation’s first Peak+ contract: 270 MW, 20 years, nuclear energy plus new capacity from 2028 · Nov 9–11 2026 · industry / grid supply

In its third-quarter results (Nov 9), Constellation said it had signed a 20-year agreement for 270 MW of “unit-contingent energy, capacity, and attributes from our existing nuclear fleet,” beginning in 2028. It is the first transaction under Peak+, which the company describes as an integrated solution that “brings together new capacity, including new generation and [demand response](https://en.wikipedia.org/wiki/Demand_response "Demand response, DR: a large customer cuts or shifts load when the grid is stressed, in exchange for payment or a better interconnection deal."), with energy products.” The customer is not named. CEO Joe Dominguez framed Peak+ as a way to pair the existing fleet with incremental capacity — batteries, generation on land around the plants, and demand response — as an alternative to new gas plants.

**Caveats.** Unit-contingent supply is only as good as the unit. The “new capacity” leg is a product description, not a named battery or DR megawatt figure in the release. A Nov 11 [Utility Dive](https://www.utilitydive.com/news/constellation-pursues-hybrid-nuclearcapacity-contracts-alongside-uprates/874408/ "Utility Dive report, Nov 11 2026, on Constellation’s Peak+ earnings-call remarks.") write-up of the earnings call adds color from Dominguez but does not identify the buyer either.

**Implication.** This is a “bring your own firm capacity” offer that still starts from the existing nuclear fleet, rather than a behind-the-meter gas island. For a campus that can offer demand response, the Peak+ wrapper is another place where a trusted cap and a bounded rebound ramp become commercial terms, not only a cluster scheduler feature.

- [Constellation: Third Quarter 2026 results (Nov 9 2026)](https://www.constellationenergy.com/news/2026/11/constellation-reports-third-quarter-2026-results.html)
- [Utility Dive: Constellation pursues hybrid capacity contracts (Nov 11 2026)](https://www.utilitydive.com/news/constellation-pursues-hybrid-nuclearcapacity-contracts-alongside-uprates/874408/)

### 4. EnerSys books a first DataSafe Noir order: 600 kW / 5 min lithium UPS cabinets · Nov 11 2026 · industry / UPS and enterprise rooms

EnerSys, reporting the quarter ended Oct 4, said it had “secured our first order for our DataSafe Noir lithium solution” and that data-center sales in its Network and Infrastructure Solutions segment grew at a double-digit rate. The product page rates DataSafe Noir at up to 600 kW per cabinet for 5 minutes at end of life, with modular builds up to 3 MW per UPS, high-rate LFP cells, a multi-level battery-management system, and [UL 1973](https://www.shopulstandards.com/ProductDetail.aspx?productId=UL1973 "UL 1973: a safety standard for batteries used in stationary and vehicle auxiliary-power applications.") certification plus [UL 9540A](https://www.ul.com/services/ul-9540a-test-method "UL 9540A: a test method for evaluating thermal runaway fire propagation in battery energy storage systems.") testing. Communications include CAN, RS-485 and dry contacts to the UPS.

**Caveats.** The order size, customer and ship date are undisclosed. The product itself is not new — product literature on the page is dated June 2026, with a user guide from September. Five minutes at 600 kW is classic UPS ride-through, not sub-millisecond GPU-step smoothing.

**Implication.** For enterprise and university rooms that will stay on AC UPS for years, a 600 kW / 5 min lithium cabinet is the practical energy store. It can cover a transfer to generators. It is not a substitute for the millisecond-to-minute products in items 1 and 2. Name the timescale before mixing them in a bill of materials.

- [EnerSys: Second Quarter Fiscal Year 2027 results (Nov 11 2026)](https://investor.enersys.com/news/news-details/2026/EnerSys-Reports-Second-Quarter-Fiscal-Year-2027-Results/default.aspx)
- [EnerSys: DataSafe Noir product page](https://www.enersys.com/en/products/batteries/datasafe/datasafe-noir/)

### 5. KAIROS, revised: context-aware caps cut agentic inference power 27% on one GPU and 46.3% on four · arXiv v2 Nov 10 (announced Nov 11) · academia / inference power capping

Yuan, Chowdhury and Talati argue that power managers built for single-turn [LLM](https://en.wikipedia.org/wiki/Large_language_model "Large language model: a transformer model used for text generation and, increasingly, tool-using agents.") serving misfire on [agentic](https://en.wikipedia.org/wiki/Intelligent_agent "Agentic AI: a workload in which a model issues many tool-interleaved, stateful calls for one user task, so context grows across turns.") work. Each request carries long-lived context that grows across tool calls. Lowering GPU frequency can push the system into a memory-thrashing regime that hurts both throughput and power. KAIROS treats agent context as a first-class signal and jointly sets GPU frequency, per-instance concurrency, and placement across instances.

The revised paper (v2, Nov 10) evaluates replayed agent traces for 3 hours on an H100 NVL server (400 W [TDP](https://en.wikipedia.org/wiki/Thermal_design_power "Thermal design power: the cooling and, in practice, the usual power-limit rating of the part.")) running [vLLM](https://docs.vllm.ai/ "vLLM: an open-source high-throughput LLM serving engine.") 0.14.0 with Qwen3-Coder-30B in FP8, plus checks on Ministral-3-14B and a Claude Code harness. Workloads are [SWE-Bench Verified](https://www.swebench.com/ "SWE-Bench Verified: a human-validated subset of GitHub-issue fixing tasks used to test coding agents."), DABStep and Terminal-Bench 2.0. Frequency and power are controlled with [Zeus](https://ml.energy/zeus/ "Zeus: a software stack for measuring and capping GPU energy and power."). On a single instance, against no frequency control and a 20 token/s per-agent P5 throughput target, KAIROS saves **27% power on average, up to 39.8%**, and meets the SLO; a fixed 810 MHz cap saves more power but misses the SLO. Across four instances at 0.16 jobs/s, average power falls from 1279.5 W with no control to 784.8 W with KAIROS plus round-robin routing, and to **686.5 W** with context-aware routing — a **46.3%** cut. P5 throughput is 26.9 token/s versus 25.4 token/s under round-robin. On SWE-Bench, a 25 token/s SLO produced no extra timeouts in the reported runs.

**Caveats.** Results are from deterministic replays of recorded traces, not a live multi-tenant cluster. Each vLLM instance uses one H100; prefill–decode disaggregation is not used. The 46.3% figure is one four-GPU point at one arrival rate. The paper first appeared in April; today’s hook is the Nov 10 revision, announced on Nov 11.

**Implication.** Agentic inference is not a softer version of decode capping. Frequency and admission have to track context growth, or a cap creates thrashing that wastes the watts you were trying to reclaim. The four-GPU result also shows that placement is a power lever: consolidating work lets some GPUs sit near idle instead of all idling “a little.” That is usable headroom for oversubscription, but only if the SLO is defined per agent, not just as cluster average tokens.

![KAIROS four-instance power comparison](fig-kairos-power.png){: w="1440" h="585" }
_Figure 2. Average power of four H100 instances at 0.16 jobs/s, from KAIROS §8.3. Context-aware routing reaches 686.5 W, 46.3% below the uncontrolled 1279.5 W._

- [arXiv 2604.16682v2: KAIROS (revised Nov 10 2026)](https://arxiv.org/abs/2604.16682)
- [HTML version](https://arxiv.org/html/2604.16682v2)

### 6. StepSplit: a closed-form Shapley bill for energy under a power cap · arXiv Nov 10 (announced Nov 11) · academia / inference energy accounting

Luo, Wang, Li, Liu and Chen start from a practical problem: GPUs report only aggregate energy, while serving engines batch requests, so providers usually bill in proportion to tokens. That allocation is unfair when requests differ in length or compute. A true [Shapley value](https://en.wikipedia.org/wiki/Shapley_value "Shapley value: a game-theory allocation that gives each player its average marginal contribution across all coalitions; here, each request’s share of batch energy.") would need $$2^{N}-1$$ GPU runs for $$N$$ requests.

They split each inference step’s energy into a shared part (mostly reading weights) and a request-specific part, and obtain a closed form: charge each request its own energy plus an equal share of the shared energy of every step it joins. A one-time microbenchmark of 2.5–17.8 minutes calibrates the split per model and GPU. Under static batching the closed form is a single pass over the scheduler log. Under continuous batching, removing a request changes later batches, so StepSplit adds a CPU-side replay correction. Against Shapley values measured in 529,513 GPU runs, $$L_1$$ error is **0.4–4.3%** for static batches of 8–256, versus **13.4–61.3%** for token-proportional allocation; under continuous batching with 8–128 requests the errors are **0.5–6.4%** versus **20.6–71.7%**.

**Caveats.** This is an accounting method, not a cap controller. The ground truth itself required more than half a million GPU runs, which is the point — the closed form is what makes Shapley usable. Results depend on the calibration remaining valid as models and engines change.

**Implication.** Once a facility or a tenant is under a power cap, “who used the joules” becomes a commercial question, including for the spot-inference pools discussed in earlier briefs. A token-proportional bill can be off by more than half. StepSplit is the metering layer those markets have been missing.

- [arXiv 2611.13802: Scaling Shapley Energy Attribution to Large LLM Batches](https://arxiv.org/abs/2611.13802)

### 7. Tapestry’s HyperQ screens 220 GW of PJM Cycle 1 site-control filings in under a day · Nov 11 2026 · adjacent / interconnection process

Tapestry reports the first operational use of HyperQ on PJM’s reformed Cycle 1 interconnection window. The tool reviewed site-control documentation for **811 generation applications, representing 220 GW**, and produced citation-backed readiness reports with a median runtime of 6 minutes 15 seconds. Tapestry compares that with a two-month manual timeline and calls it a 60× acceleration, with reports delivered overnight. Every assessment links to a page, clause or coordinate in the source filing. PJM, which keeps final compliance decisions, said the preliminary results “demonstrate a repeatable model for how AI can operate reliably under strict human governance” and a basis for its target 12-month interconnection timeline.

Tapestry is explicit about scope: these figures cover initial site-control review, not power-flow, stability or short-circuit studies. Planned next steps are technical-file validation, a pre-submission check for developers, and a shared network model.

**Caveats.** The 60× and “under a day” figures are Tapestry’s comparison with a manual baseline, not a PJM-audited productivity study. Site-control screening is the first filter, not the binding engineering study. This is about generation queues, not large-load queues.

**Implication.** Faster generation interconnection is one of the few ways to grow the firm supply that AI campuses are trying to contract (item 3). It does not relax a MW/min ramp limit at the campus fence. Treat it as a grid-side process improvement, not as a substitute for on-site smoothing.

- [Tapestry: Field Notes — HyperQ deployment in PJM’s Cycle 1](https://www.tapestryenergy.com/en/projects/field-notes-hyperq-deployment-in-pjm-s-cycle-1)

### 8. Delta’s SC26 kit: an 800 VDC, 2.5 MW in-row CDU, because the power path also has to be cooled · Nov 11 2026 · adjacent / 800 VDC thermal path

Delta Electronics will be at SC26 in Chicago (Nov 17–19) with a “from grid to chip” cooling stack aimed at 800 VDC and [±400 VDC](https://www.opencompute.org/ "OCP Mt. Diablo and related work also describe a ±400 V DC rack bus, a hyperscaler alternative to monopolar 800 VDC.") architectures. The headline unit is an 800 VDC-powered 2.5 MW in-row liquid-to-liquid CDU, with three 800 VDC, 25 kW hot-swappable pumps in a 3+0 configuration, a stated flow of up to 3,850 L/min and 60 psi at the operating point. Other exhibits include a 4U in-rack CDU at up to 200 kW, the Project Deschutes open in-row CDU at up to 2 MW (3 °C approach), a Google [OCP](https://www.opencompute.org/ "Open Compute Project: industry group that publishes open data-center hardware designs, including Mt. Diablo DC power and liquid-cooling projects.") Project Brazos liquid-to-air CDU at up to 60 kW per rack, and board-level cold plates, including a power-shelf embedded plate and a vertical-power-delivery design claimed to cool up to 3,000 W of compute and 500 W of power components in a 40 mm profile.

**Caveats.** This is a show announcement, not a field measurement. Flow, approach temperature and wattage are vendor ratings. Cooling does not itself cap or smooth IT power.

**Implication.** Once the rack and the row buses go to 800 VDC, the pumps, CDUs and power shelves become 800 VDC loads too. Protection, ride-through and step-load design have to include them. A 2.5 MW in-row CDU with 800 VDC pumps is a reminder that “the load” is not only GPUs.

- [Delta / PR Newswire: From-Grid-to-Chip cooling for 800 VDC and ±400 VDC at SC26 (Nov 11 2026)](https://www.prnewswire.com/news-releases/delta-unveils-from-grid-to-chip-cooling-innovations-for-ai-infrastructure-and-for-new-800-vdc-400-vdc-architectures-at-sc26-302935999.html)

## Spotlight: a 1 MW, 60-second hold is only 16.7 kWh

A converter can be fast and still store almost no energy. The energy that actually covers a step is

$$
E = P \times T.
$$

Vision’s stated LiLic rating — 1 MW for at least 60 seconds — is

$$
E = 1\,\mathrm{MW} \times 60\,\mathrm{s} = 16.7\,\mathrm{kWh}.
$$

Ampt’s own description of AI racks swinging between 30% and 100% of nameplate is a 0.7 MW step on a 1 MW rack. Held for the same 60 seconds, that is 11.7 kWh. Either number is small compared with a campus [BESS](https://en.wikipedia.org/wiki/Battery_storage_power_station "Battery energy storage system: a facility- or grid-scale battery used for peak shaving, smoothing and backup."), and large compared with a rack capacitor. It is also a different problem from EnerSys’s 600 kW / 5 min UPS cabinet, which stores 50 kWh of ride-through at that rating (600 kW × 5 min).

![Energy in a 60-second hold at 1 MW and 0.7 MW](fig-hold-energy.png){: w="1440" h="555" }
_Figure 3. Illustration, not a measurement. Energy in a rectangular 60-second hold at 1 MW (16.7 kWh) and at 0.7 MW (11.7 kWh)._

The practical split is then: use a sub-millisecond converter or LIC stage so the grid and the SST never see the edge of the step; size a minute-scale sidecar (or a cap ramp) for the energy; leave the 5-minute UPS for transfer to generators. Mixing those ratings in one line item is how rooms get over- or under-built.

## Bottom line

Nov 11 produced a clear hardware pair for 800 VDC smoothing: a sub-millisecond bus converter (Ampt, GA Q3 2027) and a 1 MW / 60 s white-space sidecar (Vision). Both are vendor claims, but they name the two quantities that matter — response time and stored energy. Software did not stand still. KAIROS shows that agentic inference can give back 27–46% of GPU power if the cap tracks context, and StepSplit shows how to bill those joules fairly once a cap is in place. On the grid side, Constellation is now selling nuclear energy bundled with new capacity and demand response, and Tapestry is compressing the paperwork at the front of PJM’s generation queue. Neither changes a ramp limit at the campus fence. The next design question is still the one in the Spotlight: how many milliseconds, and how many kilowatt-hours, you are actually buying.

## Glossary

- [**800 VDC**](https://www.nvidia.com/en-us/data-center/technologies/800-vdc-architecture/): Facility or row distribution at 800 V DC.
- [**BESS**](https://en.wikipedia.org/wiki/Battery_storage_power_station): Battery energy storage system.
- [**BBU**](https://www.opencompute.org/): Rack-level battery backup unit.
- [**CDU**](https://en.wikipedia.org/wiki/Liquid_cooling): Coolant distribution unit.
- [**Demand response**](https://en.wikipedia.org/wiki/Demand_response): Cutting or shifting load when the grid asks.
- [**e-Fuse**](https://en.wikipedia.org/wiki/Electronic_fuse): Semiconductor over-current protection.
- [**Grid-forming**](https://en.wikipedia.org/wiki/Grid-forming): Inverter control that sets voltage and frequency.
- [**H100**](https://www.nvidia.com/en-us/data-center/h100/): NVIDIA Hopper data-center GPU.
- [**LFP**](https://en.wikipedia.org/wiki/Lithium_iron_phosphate_battery): Lithium iron-phosphate battery chemistry.
- [**LIC**](https://en.wikipedia.org/wiki/Lithium-ion_capacitor): Lithium-ion capacitor.
- [**OCP**](https://www.opencompute.org/): Open Compute Project.
- [**PCS**](https://en.wikipedia.org/wiki/Power_conditioner): Power conversion system.
- [**Peak+**](https://www.constellationenergy.com/news/2026/11/constellation-reports-third-quarter-2026-results.html): Constellation product pairing existing nuclear energy with new capacity and demand response.
- [**PJM**](https://www.pjm.com/): Mid-Atlantic and Midwest grid operator.
- [**Shapley value**](https://en.wikipedia.org/wiki/Shapley_value): Average marginal-contribution allocation.
- [**SiC**](https://en.wikipedia.org/wiki/Silicon_carbide): Silicon carbide.
- [**Sidecar**](https://lizhouyu.github.io/technical_posts/posts/800v-dc-goes-live-calibrated-decode-caps/): A power rack next to the IT racks, often converting to 800 VDC.
- [**SLO**](https://en.wikipedia.org/wiki/Service-level_objective): Service-level objective.
- [**SST**](https://en.wikipedia.org/wiki/Solid-state_transformer): Solid-state transformer.
- [**TDP**](https://en.wikipedia.org/wiki/Thermal_design_power): Thermal design power, the usual nameplate cap of a GPU.
- [**UPS**](https://en.wikipedia.org/wiki/Uninterruptible_power_supply): Uninterruptible power supply.
- [**vLLM**](https://docs.vllm.ai/): Open-source LLM serving engine.
- [**VRM**](https://en.wikipedia.org/wiki/Voltage_regulator_module): Voltage regulator module at the point of load.

---

_How useful was today's brief? Reply in Grok Bot chat with an overall rating (1–5) and, if you like, per-item ratings (1–5)._
