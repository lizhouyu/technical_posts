---
title: "Tesla’s Powercore goes straight to 800 VDC; flexibility’s capacity credit is not the offered MW"
date: 2026-11-19 08:30:00 +0800
categories: [Daily Brief, Power]
tags: [800vdc, SST, ramp-smoothing, energy-storage, grid, capacity-credit, AIDC-infra, industry, academia, carbon]
description: "A 5-minute cut. Tesla’s 17 November RE+ announcement of Powercore is a vendor-claimed 7.4 MW / 9 MVA solid-state transformer, inverter and breaker from 10–34.5 kV AC to 800–2,000 VDC, with first units operating in 2027 and Megapack on the DC bus for load smoothing. Sungrow’s 18 November release shows EnerNeo (1.5–6 MW, MV AC to 800 VDC) plus three BESS architectures for dynamic load smoothing. Zahner et al. (arXiv 2611.21982) cut VRM loop inductance nearly in half by moving the regulator under the die. Ren et al. (2611.22814) show eight-hour deferral credits 28.84 MW versus 3.08 MW for a 10-minute UPS at the same 113.129 MW interconnection reduction. A Google-led v2 paper (2601.17990) finds average-carbon load shaping can raise ERCOT emissions at a fossil-heavy node."
media_subpath: /assets/img/briefs/2026-11-19/
image:
  path: fig-elcc-dc-flexibility.png
  alt: Effective load-carrying capability of data-centre flexibility at a shared 113.129 MW point-of-interconnection reduction, from Ren et al., arXiv 2611.22814, Table II
math: true
---

## At a glance

- **Tesla names a one-step path to 800 VDC, on paper.** On Nov 17, at [RE+](https://www.re-plus.com/ "RE+: North America’s largest clean-energy exhibition; the 2026 show ran 16–19 November at the Las Vegas Convention Center."), [Tesla](https://x.com/Tesla_Megapack "Tesla Megapack: Tesla Energy’s official account, which issued the Powercore announcement.") introduced [Powercore](https://x.com/Tesla_Megapack/status/2122721563493744771 "Tesla Megapack post, 17 Nov 2026, 16:00 UTC: Powercore product announcement.") as a 7.4 MW / 9 MVA [solid-state transformer](https://en.wikipedia.org/wiki/Solid-state_transformer "Solid-state transformer (SST): a power-electronic transformer that converts medium-voltage AC to a controlled DC or AC output in one conversion stage."), inverter and breaker, 10–34.5 kV AC to 800–2,000 VDC, with first units operating in 2027. [Megapack](https://x.com/Tesla_Megapack/status/2122738271256211706 "Tesla Megapack article, 17 Nov 2026, ‘The Future Runs on Powercore,’ posted at 17:06 UTC.") on the DC bus is the claimed [load-smoothing](https://lizhouyu.github.io/technical_posts/posts/aidc-power-ramp-smoothing/ "Load smoothing: using storage or scheduling so a hall’s import ramp stays inside a grid or interconnect limit.") buffer. No named customer or in-service hall.
- **Sungrow shows the same SST-plus-battery menu.** An 18 November release presents [EnerNeo](https://www.sungrowpower.com/en/powering-ahead-sungrow-demonstrates-resilience-and-innovation-at-re-2026 "Sungrow RE+ 2026 release, 18 Nov 2026: EnerNeo SST and three AIDC BESS architectures.") as a 1.5–6 MW modular SST from medium-voltage AC to 800 VDC, plus three [BESS](https://en.wikipedia.org/wiki/Grid_energy_storage "Battery energy storage system (BESS): a battery plus inverter used for backup, ramp smoothing or grid services.") architectures for dynamic load smoothing. EnerNeo launched in July; this is a showcase, not a new hall.
- **Offered flexible MW is a poor adequacy metric; average carbon intensity can backfire.** [Ren, Sun, Wu and Wang](https://arxiv.org/abs/2611.22814 "Ren, Sun, Wu and Wang, Capacity Credit of Data-Centre Flexibility, arXiv 2611.22814, announced 18 Nov 2026.") give eight-hour deferral an [ELCC](https://en.wikipedia.org/wiki/Capacity_credit "Effective load-carrying capability (ELCC): additional rigid demand a resource can support at the same reliability, usually equal expected unserved energy.") of 28.84 MW versus 3.08 MW for a 10-minute [UPS](https://en.wikipedia.org/wiki/Uninterruptible_power_supply "Uninterruptible power supply (UPS): a battery-backed converter that holds up IT load through a short grid or facility disturbance."), at the same 113.129 MW interconnection reduction. A [Google](https://arxiv.org/abs/2601.17990 "Chen, Radovanović and coauthors, A Cherry-Picking Approach to Large Load Shaping for More Effective Carbon Reduction, arXiv 2601.17990v2, listed 18 Nov 2026.")-led v2 paper finds that average-carbon shaping of a 400 MW load increases [ERCOT](https://en.wikipedia.org/wiki/Electric_Reliability_Council_of_Texas "ERCOT: the grid operator for most of Texas.") emissions by 8.8 ktCO2/yr at a fossil-heavy node.

## Key developments

### 1. Tesla announces Powercore, a 7.4 MW SST from medium-voltage AC to 800 VDC · Nov 17 2026 · industry / hall–grid

At RE+, Tesla’s Megapack account introduced Powercore as a “solid state medium voltage transformer, inverter and breaker,” vendor-rated at “7.4 MW/9 MVA continuously at 34.5 kVac w/ grid-forming support for 10MVA of peak power,” with first units “Operating 2027.” The official article adds a claimed 98.86 percent peak efficiency. For AI halls, Tesla says Powercore “gets there in one step, from the medium-voltage feeder straight to 800 Vdc,” and that operators can “pair it with Megapack directly on the DC bus for backup, load smoothing, and other applications.” It is “collaborating with [Nvidia](https://developer.nvidia.com/blog/nvidia-800-v-hvdc-architecture-will-power-the-next-generation-of-ai-factories/ "NVIDIA blog on an 800 V HVDC architecture for AI factories; used here as the first-party 800 VDC reference, not a Powercore datasheet.")” on 800 VDC architectures; Megapack is already qualified under NVIDIA’s DSX Ready program, but Powercore is not claimed as already qualified. In a same-day [*pv magazine USA*](https://pv-magazine-usa.com/2026/11/17/exclusive-tesla-unveils-powercore-medium-voltage-power-electronics-platform-at-re-2026/ "Zientara, pv magazine USA, 17 Nov 2026: on-the-record interview with AJ Booth.") interview, AJ Booth said the breaker “can clear electrical faults in 100 microseconds.” No customer, price or factory is named; 2027 operation is a vendor claim.

The bid matches yesterday’s [Vertiv](https://lizhouyu.github.io/technical_posts/posts/vertiv-800vdc-three-scales-miso-nyiso-flex-lvrt/ "Nov 18 brief: Vertiv’s 17 Nov SC26 800 VDC stack, with smoothing claimed only when storage sits on the 800 VDC bus.") stack: one SST stage, then stored energy on the 800 VDC bus to absorb step loads. Whether that buffer lets a hall run closer to its interconnect cap is not measured here.

**Sources:** [Tesla product post, 17 Nov 2026](https://x.com/Tesla_Megapack/status/2122721563493744771 "Official product post with the 7.4 MW / 9 MVA and 2027 operating claims."); [Tesla article, 17 Nov 2026](https://x.com/Tesla_Megapack/status/2122738271256211706 "Official article, ‘The Future Runs on Powercore.’"); [*pv magazine USA*, 17 Nov 2026](https://pv-magazine-usa.com/2026/11/17/exclusive-tesla-unveils-powercore-medium-voltage-power-electronics-platform-at-re-2026/ "Booth interview, including the 100-microsecond breaker claim.").

### 2. Sungrow presents EnerNeo and three BESS architectures for AI-hall load smoothing · Nov 18 2026 · industry / ramp-smoothing

[Sungrow](https://www.sungrowpower.com/en/powering-ahead-sungrow-demonstrates-resilience-and-innovation-at-re-2026 "Sungrow: PV inverter and energy-storage vendor; first-party RE+ 2026 release dated 18 Nov 2026.")’s RE+ release presents EnerNeo as a modular SST that “offers 1.5–6 MW power range and simplifies power delivery by converting medium-voltage AC directly into 800V DC,” plus three complementary BESS architectures — [grid-forming](https://en.wikipedia.org/wiki/Grid-forming "Grid-forming: inverter controls that set voltage and frequency, rather than following an existing grid waveform.") BESS, MV-UPS + BESS, and Dual-[PCS](https://en.wikipedia.org/wiki/Power_electronics "Power conversion system (PCS): the inverter/rectifier stage of a battery system. Dual-PCS places conversion on both the grid and IT sides.") + BESS — that “support dynamic load smoothing, grid support, and power resilience.” EnerNeo launched in July 2026; the 18 November text names no North American site or measured ramp result.

The useful signal is the menu: vendors are selling SST-to-800 VDC plus a choice of where the battery sits, specifically for AI load transients. This is a showcase, not a new in-service hall.

**Primary source:** [Sungrow, 18 Nov 2026](https://www.sungrowpower.com/en/powering-ahead-sungrow-demonstrates-resilience-and-innovation-at-re-2026 "First-party RE+ 2026 release describing EnerNeo and the three AIDC BESS architectures.").

### 3. Moving the VRM under the die cuts loop inductance nearly in half · Nov 18 2026 · academia / server–PoL

Zahner, Habibi and Ferdowsi at [Missouri S&T](https://ece.mst.edu/ "Missouri University of Science and Technology, Department of Electrical and Computer Engineering.") (arXiv [2611.21982](https://arxiv.org/abs/2611.21982 "Zahner, Habibi and Ferdowsi, Emerging Vertical Power Delivery in AI Data Centers: Challenges and Solutions, arXiv 2611.21982, announced 18 Nov 2026. Submitted to the IEEE for possible publication.")) review [800 VDC](https://developer.nvidia.com/blog/nvidia-800-v-hvdc-architecture-will-power-the-next-generation-of-ai-factories/ "800 VDC: high-voltage DC rack and facility distribution, aimed at lower current than low-voltage AC or 54 V paths.") delivery down to the [point of load](https://en.wikipedia.org/wiki/Voltage_regulator_module "Point-of-load (PoL) converter: the last voltage-regulator stage, placed next to the processor or other load.") and compare lateral versus vertical regulator placement in Cadence Sigrity PowerSI simulations (each VRM replaced by its 220 μF output capacitor). Table V reads loop inductance from the imaginary impedance at 1 MHz: a lateral [VRM](https://en.wikipedia.org/wiki/Voltage_regulator_module "Voltage regulator module (VRM): the board-level converter that steps a bus voltage down to the processor rail.") 50 mm from the die is 3.36 nH, falling to 1.77 nH when the regulator sits under the die. In a complete [PDN](https://en.wikipedia.org/wiki/Power_integrity "Power delivery network (PDN): the path from the facility or rack bus through planes, capacitors and regulators to the die; power-integrity studies analyse its impedance."), that move lowers only the low-frequency anti-resonant peak. The simulations describe passive impedance, not a measured GPU rack.

Hall-level SSTs do not by themselves contain a decode or prefill current step at the die. A cap or oversubscription policy that ignores loop inductance will still see voltage droop at the processor.

**Primary source:** [arXiv 2611.21982](https://arxiv.org/abs/2611.21982 "Abstract and PDF for Zahner, Habibi and Ferdowsi.").

### 4. Eight-hour deferral credits 28.84 MW; a 10-minute UPS credits 3.08 MW, at the same 113.129 MW cap · Nov 18 2026 · academia / grid flexibility

Ren, Sun, Wu and Wang at the [University of Edinburgh](https://www.eng.ed.ac.uk/ "University of Edinburgh School of Engineering.") (arXiv [2611.22814](https://arxiv.org/abs/2611.22814 "Ren, Sun, Wu and Wang, Capacity Credit of Data-Centre Flexibility, arXiv 2611.22814, announced 18 Nov 2026.")) estimate ELCC for workload deferral, a fixed evening reduction, UPS energy above a protected backup floor, and dedicated BESS, all under one point-of-interconnection import-reduction rating. The case is a 2035 “Holistic Transition” [copperplate](https://en.wikipedia.org/wiki/Electrical_grid "Copperplate model: a power-system study with no transmission constraints, so only energy adequacy is tested.") study using [NESO](https://en.wikipedia.org/wiki/National_Energy_System_Operator "National Energy System Operator (NESO): Great Britain’s electricity system operator.") scenarios. Table I yields a POI reduction P = 113.129 MW. Table II, plotted in Figure 1, then reports eight-hour deadline deferral at 28.84 MW ELCC versus 8.36 MW for a fixed evening cap that “shifts over twenty times the work,” 3.08 MW for a 10-minute UPS (five minutes reserved for backup), and 25.96 MW for an eight-hour dedicated battery. This is a simulation with design-choice workload fractions, not a measured hall, and it does not distinguish training from inference.

Flexible interconnection that credits offered MW, or that treats UPS nameplate as an adequacy resource, will overstate short-duration backup and understate optional, longer-deadline compute flexibility.

**Primary source:** [arXiv 2611.22814](https://arxiv.org/abs/2611.22814 "Abstract and PDF for Ren, Sun, Wu and Wang, including Table II.").

![Effective load-carrying capability of data-centre flexibility at a shared 113.129 MW point-of-interconnection reduction](fig-elcc-dc-flexibility.png){: w="1623" h="762" }
_Figure 1. ELCC at the same 113.129 MW POI reduction (Ren et al., arXiv 2611.22814, Table II). Eight-hour deferral credits 28.84 MW; a 10-minute UPS credits 3.08 MW. Copperplate Great Britain 2035 simulation, not a measured hall._

### 5. Average-carbon load shaping can raise ERCOT emissions; a cherry-pick rule beats static LMP by 2–3 times · Nov 18 2026 · adjacent / carbon

Chen, Radovanović and coauthors at Google, with Electric Power Engineers (arXiv [2601.17990v2](https://arxiv.org/abs/2601.17990 "Chen, Radovanović and coauthors, A Cherry-Picking Approach to Large Load Shaping for More Effective Carbon Reduction, arXiv 2601.17990v2. v1 submitted 25 Jan 2026; v2 submitted 16 Nov 2026 and listed 18 Nov. No DOI on the abs page.")), replace the January preprint with a material rewrite. They run year-long counterfactuals on a nearly 8,900-bus replica of ERCOT’s 2023 day-ahead [SCUC](https://en.wikipedia.org/wiki/Unit_commitment_problem_in_electrical_power_production "Security-constrained unit commitment (SCUC): the day-ahead market problem that starts and stops generators subject to transmission limits.") / [SCED](https://en.wikipedia.org/wiki/Economic_dispatch "Security-constrained economic dispatch (SCED): the intra-day dispatch of already-committed generators, subject to transmission limits.") process. Flexible load is a 400 MW baseline at each of two nodes, allowed to move between 320 and 480 MW while preserving daily energy: Tesla, a renewable-rich NORTH-zone node the authors identify as a Google data-centre location, and Tylergnd in the fossil-heavy EAST zone. An optimization-based upper bound saves 65.4 ktCO2/yr at Tesla and 36.4 at Tylergnd. Static [LMP](https://en.wikipedia.org/wiki/Locational_marginal_pricing "Locational marginal price (LMP): the nodal wholesale electricity price, including congestion and losses.") shaping saves 20.8 and 6.3 kt. Grid-average carbon intensity saves 10.9 kt at Tesla but increases emissions by 8.8 ktCO2/yr at Tylergnd. A daily cherry-pick rule saves 42.9 and 18.9 kt — about 2–3 times static LMP — with stated wholesale price impacts of at most USD 0.6/MWh for a single 400 MW load. This is a 2023 market simulation, not a measured production shift.

A hall that shapes or sites load on a zonal average-carbon feed can raise system emissions in a congested, fossil-heavy zone. That matters for [Scope 2](https://ghgprotocol.org/corporate-standard "Scope 2: greenhouse-gas accounting for purchased electricity under the GHG Protocol Corporate Standard. The authors argue that average-intensity signals can be a poor guide.") claims and for flexibility credited on emissions, not just MW.

**Primary source:** [arXiv 2601.17990v2](https://arxiv.org/abs/2601.17990 "Current v2 abstract and PDF.").

## Spotlight: capacity credit is not the offered MW

At a shared interconnection rating $$P$$, average capacity credit is

$$\mathrm{CC}_{\mathrm{avg}} = \mathrm{ELCC}/P.$$

In arXiv 2611.22814, $$P = 113.129$$ MW for every service in Table II, so Figure 1 already shows the ratio: 25.49 percent for eight-hour deferral, 22.94 percent for an eight-hour battery, 7.39 percent for a firm evening cap, and 2.72 percent for a 10-minute UPS. The evening service moves more work and still delivers less adequacy, because recovery can land in a later shortage. Tesla’s and Sungrow’s 800 VDC plus BESS pitches address a different timescale — seconds-to-minutes ramps — which this ELCC study does not measure.

## Bottom line

Tesla has named an SST that claims a one-step path from the medium-voltage feeder to 800 VDC, with Megapack on that bus for smoothing; Sungrow is selling the same split, with three explicit battery placements. Both are show or 2027 claims, not in-service halls, and they sit beside yesterday’s Vertiv stack rather than replacing it. The new papers say what those flexibility claims are worth if treated as grid products: duration and optionality dominate offered MW for adequacy, the last centimeters of the PDN still set droop at the die, and a naive average-carbon cap can increase emissions. Industrial numbers are vendor claims; academic numbers are simulations.

## Also noted

- Ko and Zhu (arXiv [2611.22056](https://arxiv.org/abs/2611.22056 "Ko and Zhu, Grid-Aware Assessment of Forced Oscillations from Spatially Distributed Large Loads, arXiv 2611.22056, announced 18 Nov 2026.")): under a conservative 0.02 Hz threshold, deterministic upper-bound admissible swings are as low as 21.6 MW on the IEEE 39-bus system and 13.6 MW on a 14-generator Australian system (square-wave cases). Simulated test systems, not a recorded AI-hall event.
- Sun, Jiang, Zhang, Bai, Liu, Buyya and Toosi (arXiv [2611.21165](https://arxiv.org/abs/2611.21165 "Sun et al., A Matter of Stages: Energy–Latency Trade-offs in Multimodal LLM Serving, arXiv 2611.21165, announced 17 Nov 2026.")): on a three-GPU multimodal serving study, [EPD](https://arxiv.org/abs/2611.21165 "EPD disaggregation: running visual encode, prefill and decode on separate GPUs so each stage can be provisioned and frequency-scaled on its own.") disaggregation cuts GPU energy per successful request by 13.3–37.0 percent at nearly identical output-token throughput, but raises mean time-to-first-token; uniform downclocking to 80 percent saves 11.7–18.6 percent. Not a hall-scale result.

## Glossary

- [**800 VDC**](https://developer.nvidia.com/blog/nvidia-800-v-hvdc-architecture-will-power-the-next-generation-of-ai-factories/ "800 VDC: high-voltage DC rack and facility distribution."): High-voltage DC rack and facility distribution.
- [**BESS**](https://en.wikipedia.org/wiki/Grid_energy_storage): Battery energy storage system.
- [**DSX Ready**](https://developer.nvidia.com/blog/nvidia-800-v-hvdc-architecture-will-power-the-next-generation-of-ai-factories/ "DSX Ready: Tesla’s wording for an NVIDIA qualification program for next-generation data-center equipment. Tesla says Megapack already qualifies; it does not say Powercore already does."): NVIDIA qualification program, as named by Tesla.
- [**ELCC**](https://en.wikipedia.org/wiki/Capacity_credit): Effective load-carrying capability.
- [**EPD**](https://arxiv.org/abs/2611.21165): Encode–prefill–decode disaggregation in multimodal serving.
- [**ERCOT**](https://en.wikipedia.org/wiki/Electric_Reliability_Council_of_Texas): Grid operator for most of Texas.
- [**Grid-forming**](https://en.wikipedia.org/wiki/Grid-forming): Inverter controls that set voltage and frequency.
- [**LMP**](https://en.wikipedia.org/wiki/Locational_marginal_pricing): Locational marginal price.
- [**NESO**](https://en.wikipedia.org/wiki/National_Energy_System_Operator): Great Britain’s electricity system operator.
- [**PCS**](https://en.wikipedia.org/wiki/Power_electronics): Power conversion system.
- [**PDN**](https://en.wikipedia.org/wiki/Power_integrity): Power delivery network, from facility bus to the die.
- [**POI**](https://en.wikipedia.org/wiki/Electrical_grid): Point of interconnection with the grid.
- [**Powercore**](https://x.com/Tesla_Megapack/status/2122721563493744771 "Tesla’s solid-state medium-voltage platform: transformer, inverter and breaker in one enclosure, vendor-rated at 7.4 MW / 9 MVA."): Tesla’s solid-state medium-voltage platform.
- [**RE+**](https://www.re-plus.com/): North American clean-energy exhibition.
- [**SCED**](https://en.wikipedia.org/wiki/Economic_dispatch): Security-constrained economic dispatch.
- [**Scope 2**](https://ghgprotocol.org/corporate-standard): Accounting for purchased electricity emissions.
- [**SCUC**](https://en.wikipedia.org/wiki/Unit_commitment_problem_in_electrical_power_production): Security-constrained unit commitment.
- [**SST**](https://en.wikipedia.org/wiki/Solid-state_transformer): Solid-state transformer.
- [**Sungrow**](https://www.sungrowpower.com/en/): PV inverter and energy-storage vendor.
- [**Tesla**](https://x.com/Tesla_Megapack): Maker of Powercore and Megapack.
- [**UPS**](https://en.wikipedia.org/wiki/Uninterruptible_power_supply): Uninterruptible power supply.
- [**VRM**](https://en.wikipedia.org/wiki/Voltage_regulator_module): Voltage regulator module.
- [**VPD**](https://arxiv.org/abs/2611.21982): Vertical power delivery, with the regulator under the die.

---

_How useful was today’s brief? Reply in Grok Bot chat with an overall rating (1–5) and, if you like, per-item ratings (1–5)._
